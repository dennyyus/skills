# Operational gotchas

Traps that silently waste time. Both sections are written from failures that actually happened, not theory.

## Contents

- [Browser and viewport](#browser-and-viewport)
- [Notion](#notion)
- [A working loop](#a-working-loop)

---

## Browser and viewport

Getting a genuine mobile viewport is harder than it looks, and the failure modes are quiet. Settle this **before** starting the walkthrough — discovering it halfway through means redoing the run.

### `resize_window` no-ops on a maximised window

It reports success and nothing happens. The call changes window bounds but never restores the window state, so the OS keeps it snapped full-screen.

**Detect it:** after resizing, check `window.innerWidth` rather than trusting the response.

```js
({inner:[innerWidth,innerHeight], outer:[outerWidth,outerHeight]})
```

`outer` at roughly screen size (e.g. 1920×1032 on a 1920×1080 display) is the maximised signature. Only the human can un-maximise — ask them to double-click the title bar.

### DevTools blocks mouse input entirely

With DevTools attached, `Input.dispatchMouseEvent` hangs and times out after 30 seconds, **while JavaScript execution, screenshots and navigation all keep working normally.**

That asymmetry is the diagnostic: if clicks and typing are the only thing failing, DevTools is the first suspect. Nothing else produces that pattern.

Device mode is the tempting workaround — it gives an accurate viewport and DPR — but it's mutually exclusive with driving the page. Pick one.

### DevTools docked to the side fakes a narrow viewport

A docked panel shrinks `innerWidth` while `outerWidth` stays full. You get a narrow viewport that isn't a narrow window, mobile media queries fire correctly, and input is dead. Easy to misread as success.

**Detect it:** a large gap between `outer` and `inner` width. 1920 outer against 374 inner means a panel is eating 1546px.

### Chrome enforces a minimum window width

Roughly 670px outer, ~647px inner, observed on Windows. You cannot reach 390px by resizing, no matter how many times you try.

647px does activate most mobile breakpoints (usually ≤768px), so the mobile *layout* renders — but column widths, touch-target relationships and anything below ~600px won't match a real phone. Say so in the log rather than passing it off as a phone run.

### Page-zoom shortcuts are blocked

`ctrl+plus` would shrink the CSS viewport and make media queries fire at phone widths inside a wider window. The keyboard shortcut is rejected. CSS `zoom` on an element doesn't help either — media queries evaluate against the viewport, not a scaled element.

### What this means in practice

A true phone viewport usually needs the human — either resizing the window by hand, or running the flow on an actual phone and sending screenshots. **Ask early.** The sequence that wastes the most time is discovering each of the above one at a time across several turns.

If the human supplies the screenshots, that's a good outcome, not a fallback: they get a real device, real UA, real touch behaviour and real in-app browsers, none of which a desktop Chrome window reproduces.

---

## Notion

### Fetching a large page exceeds the token limit

`notion-fetch` on a page with many images returns 50k+ characters (signed image URLs are ~1500 chars each) and gets written to a file instead of returned.

Don't read that file back in chunks. Parse it with a script and extract only what's needed:

```python
import re, json, sys
raw = open(path, encoding='utf-8').read()
try:    s = json.loads(raw)['text']
except Exception: s = raw.encode().decode('unicode_escape', errors='ignore')

# exact source of a block, for use as old_str
i = s.find('### Bigger bugs')
print(repr(s[i:s.index('### Delight')]))
```

`repr()` matters — it shows the exact whitespace and escaping, which is what the edit API matches against.

### Edits match the stored source byte-for-byte, and the stored source isn't what you wrote

`update-page` with `update_content` is search-and-replace against Notion's internal markdown. Three things differ from what you sent:

| You write | Notion stores |
|---|---|
| Markdown tables with `\|` pipes | `<table><tr><td>…</td></tr></table>` XML |
| `S$105` | `S\$105` (escaped dollar) |
| Blank line between heading and bullets | Often a single newline |

Trying to edit a table row with pipe syntax matches nothing. Always read the stored source first.

### Multiple edits in one call fail silently

**This is the one that causes real damage.** When a single `update_content` call carries several `content_updates`, non-matching entries are dropped while the matching ones apply — and the call still returns a success response with the page ID.

The same non-matching edit sent alone returns a loud `validation_error`. So the failure only appears in batches, which is exactly when you're least likely to check.

**Always verify against the rendered page after editing.** Cheap check via the browser:

```js
const t = document.body.innerText;
JSON.stringify({
  'new text present': /distinctive phrase from the edit/.test(t),
  'old text gone':   !/distinctive phrase being replaced/.test(t)
}, null, 1)
```

Note that emoji often don't appear in `innerText` at all, so counting 🔴/🟡 markers this way returns zero and means nothing. Check for text, not symbols.

### You can't see images through the API

`notion-fetch` returns image URLs, never the pictures. Writing captions or findings from filenames alone means inventing them.

To actually look at a page, open it in the browser and screenshot it. This also lets you read screenshots a human pasted in, which is otherwise impossible.

### Images can't be moved, only re-placed

There's no block-move operation. Rearranging images means re-uploading them and rewriting the block that holds them.

`notion-create-attachment` accepts inline text or a **public HTTPS URL** — not local files. So for screenshots that live on disk, either:

1. **Have the human paste them in.** Usually correct. Two minutes of drag-and-drop against a fragile multi-step rebuild.
2. **Re-upload from the page's own signed URLs.** If the images are already in Notion, `notion-fetch` returns signed S3 links you can feed straight back into `create-attachment`. These expire in **300 seconds**, so fetch, extract, and fire all the uploads in one batch. Do all uploads *before* the `replace_content` call — if uploads fail, the page is still intact.

Full-page `replace_content` deletes every image not referenced in the new content. Never call it on a page with images you haven't re-uploaded.

---

## A working loop

For any non-trivial Notion edit:

1. `notion-fetch` → it writes to a file
2. Parse that file with a script, print `repr()` of the exact block you intend to change
3. `update-page` with `old_str` copied from that output
4. Verify in the browser
5. Only then report it as done

Steps 2 and 4 feel like overhead. They cost less than telling someone their document is updated when it isn't.

# Skills

Custom Claude Code skills for product work — problem validation, product strategy, judgment, and teaching.

Each skill is a folder containing a `SKILL.md`, plus a `references/` directory where the skill loads detail only when it's needed. The `SKILL.md` frontmatter describes what each one does and when it triggers — read that rather than a summary here.

## Install

Copy the skill folders you want into your Claude Code skills directory:

```bash
cp -r <skill-name> ~/.claude/skills/
```

Claude picks them up on the next session. Skills trigger automatically from their description, or you can invoke one by name with `/<skill-name>`.

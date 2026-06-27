# Repository Guidelines

## Project Scope

This repository packages the `audit-ai-writing` Codex skill. Keep it focused on auditing and revising drafts for AI-writing tells, especially reader-facing article drafts.

## Project Structure

- `SKILL.md`: skill manifest and operating guide. Update this when trigger behavior, workflow, output style, or guardrails change.
- `references/signs-of-ai-writing.md`: detailed review checklist. Put concrete patterns, examples, and fix rules here instead of bloating `SKILL.md`.
- `agents/openai.yaml`: UI metadata for Codex. Update only when the display name, short description, default prompt, or invocation policy changes.

Do not add broad documentation files such as `README.md`, `TODO.md`, or `CHANGELOG.md` unless the user explicitly asks for them.

## Editing Rules

Keep changes small and traceable to real usage feedback. Prefer improving the checklist or workflow over adding scripts or new directories. Do not turn the skill into an AI detector; it reviews writing patterns and publication quality, not authorship certainty.

For public article drafts, preserve the publication boundary: published text should speak from the author to readers, not from an assistant, editor, reviewer, Codex, Claude, or agent to the author.

## Validation

Run the skill validator after edits:

```bash
/usr/bin/python3 /Users/xingshuhao/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/xingshuhao/skill/audit-ai-writing
```

The default Homebrew Python on this machine may not have `yaml`; `/usr/bin/python3` currently can load the existing PyYAML install.

## Git And Release Notes

Use short conventional commits such as `docs: add repository guidelines` or `docs: refine audience boundary checks`.

Before pushing to GitHub or changing public repository settings, confirm with the user. This skill may be symlinked into Codex at:

```text
/Users/xingshuhao/.codex/skills/audit-ai-writing -> /Users/xingshuhao/skill/audit-ai-writing
```

# Audit AI Writing

A Codex skill for reviewing drafts for common AI-writing tells and publication-boundary leaks.

It is based on the Wikipedia field guide [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), but it is not an AI detector. The skill treats those signs as editing heuristics: it helps improve drafts, tighten claims, remove generic AI phrasing, and catch assistant/editor notes that accidentally leak into reader-facing prose.

## What It Checks

- Inflated or unsupported significance claims
- Generic AI vocabulary and over-smooth transitions
- Promotional tone, vague attribution, and formulaic endings
- Markdown, citation, or tool artifacts left in prose
- Publication-boundary leaks, such as instructions to the author, editor comments, or model self-talk inside the article

## Installation

Clone the repository wherever you keep local skills:

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/skill/audit-ai-writing
```

Then expose it to Codex with a symlink:

```bash
ln -s ~/skill/audit-ai-writing ~/.codex/skills/audit-ai-writing
```

Restart Codex or open a new session if the skill list does not refresh immediately.

## Usage

Ask Codex to use the skill explicitly:

```text
Use $audit-ai-writing to review this draft for signs of AI writing and suggest concrete edits:

...
```

For rewrite requests, the skill should preserve the author's intent and voice. For review requests, it should report actionable issues and provide direct replacements.

## 中文说明

这个 skill 适合中文/英文文章发布前审稿，尤其适合检查 AI 写作常见问题，以及“本来是 AI 助手对作者说的话，误写进正文里”的发布语境污染。

推荐安装方式是：把仓库 clone 到自己的 skill 源目录，再用 symlink 暴露给 Codex。symlink 是本机安装方式，不需要提交进仓库。

## Development

Validate after edits:

```bash
/usr/bin/python3 /Users/xingshuhao/.codex/skills/.system/skill-creator/scripts/quick_validate.py /Users/xingshuhao/skill/audit-ai-writing
```

The repository includes:

```text
SKILL.md
agents/openai.yaml
references/signs-of-ai-writing.md
AGENTS.md
```

`AGENTS.md` is for coding agents that maintain this repository. End users can start with this README and `SKILL.md`.

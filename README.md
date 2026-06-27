# Audit AI Writing

English | [中文](#中文) | [日本語](#日本語) | [한국어](#한국어)

A Codex skill for reviewing drafts for common AI-writing tells and publication-boundary leaks.

It is based on the Wikipedia field guide [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), but it is not an AI detector. The skill treats those signs as editing heuristics: it helps improve drafts, tighten claims, remove generic AI phrasing, and catch assistant/editor notes that accidentally leak into reader-facing prose.

## What It Checks

- Inflated or unsupported significance claims
- Generic AI vocabulary and over-smooth transitions
- Promotional tone, vague attribution, and formulaic endings
- Markdown, citation, or tool artifacts left in prose
- Publication-boundary leaks, such as instructions to the author, editor comments, or model self-talk inside the article

## Installation

Clone the repository directly into your Codex skills directory:

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

Restart Codex or open a new session if the skill list does not refresh immediately.

## Usage

Ask Codex to use the skill explicitly:

```text
Use $audit-ai-writing to review this draft for signs of AI writing and suggest concrete edits:

...
```

For rewrite requests, the skill should preserve the author's intent and voice. For review requests, it should report actionable issues and provide direct replacements.

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

If you prefer to keep editable skill sources elsewhere, use a symlink-based development install:

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/skill/audit-ai-writing
ln -s ~/skill/audit-ai-writing ~/.codex/skills/audit-ai-writing
```

## 中文

这是一个 Codex skill，用来在文章发布前审查常见 AI 写作痕迹和发布语境污染。

它参考 Wikipedia 的 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)，但它不是 AI 检测器。它不会判断一篇文章是不是 AI 写的，而是把这些迹象当作编辑启发式：帮你删掉空泛表达、收紧事实主张、减少模板化 AI 腔，并检查“本来是助手或编辑对作者说的话”有没有误写进正文。

### 检查内容

- 被夸大的重要性，或没有证据支撑的宏大判断
- 常见 AI 词汇、过度顺滑的转场、公式化结尾
- 宣传腔、模糊归因、缺少具体事实的分析
- Markdown、引用、工具输出痕迹残留
- 发布语境污染，例如对作者的指令、编辑备注、模型自述混进文章

### 安装

把仓库直接 clone 到 Codex 的 skills 目录：

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

如果 skill 列表没有立刻刷新，重启 Codex 或开启一个新会话。

### 用法

显式要求 Codex 使用这个 skill：

```text
Use $audit-ai-writing to review this draft for signs of AI writing and suggest concrete edits:

...
```

如果是改写请求，skill 会尽量保留作者原意和声音。如果是审稿请求，它会列出可执行问题和可直接替换的写法。

## 日本語

これは、公開前の原稿に含まれる典型的な AI 文章らしさや、公開文に混入した編集メモを確認するための Codex skill です。

Wikipedia の [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) を参考にしていますが、AI 検出器ではありません。文章の作者を断定するものではなく、編集上のヒューリスティックとして使います。曖昧な表現、根拠の弱い主張、定型的な AI 風表現、読者向け本文に紛れ込んだアシスタントや編集者向けの発話を見つけやすくします。

### チェック内容

- 根拠のない大げさな重要性の主張
- AI らしい語彙、滑らかすぎる接続、定型的な結論
- 宣伝調、曖昧な帰属、具体性のない分析
- Markdown、引用、ツール出力の残骸
- 著者への指示、編集メモ、モデルの自己言及が本文に混入している箇所

### インストール

Codex の skills ディレクトリに直接 clone します:

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

skill 一覧にすぐ表示されない場合は、Codex を再起動するか新しいセッションを開いてください。

### 使い方

Codex に明示的に skill の使用を依頼します:

```text
Use $audit-ai-writing to review this draft for signs of AI writing and suggest concrete edits:

...
```

リライトでは著者の意図と声をできるだけ保ちます。レビューでは、実際に直せる問題点と置き換え案を出します。

## 한국어

이 Codex skill은 공개 전 초안에서 흔한 AI 문체의 흔적과, 독자용 본문에 섞여 들어간 편집 메모나 어시스턴트의 말을 점검하기 위한 도구입니다.

Wikipedia의 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)을 참고하지만, AI 탐지기는 아닙니다. 글쓴이를 판정하지 않고, 편집을 위한 휴리스틱으로 사용합니다. 모호한 표현, 근거가 약한 주장, 전형적인 AI식 문장, 저자나 편집자를 향한 말이 본문에 남아 있는 문제를 찾는 데 도움을 줍니다.

### 점검 항목

- 근거 없이 과장된 중요성 주장
- AI식 어휘, 지나치게 매끄러운 전환, 공식적인 결론
- 홍보성 문체, 모호한 출처 표현, 구체성이 부족한 분석
- Markdown, 인용, 도구 출력 흔적
- 저자 지시, 편집자 메모, 모델의 자기 언급이 독자용 본문에 섞인 경우

### 설치

Codex skills 디렉터리에 바로 저장소를 clone합니다:

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

skill 목록이 바로 갱신되지 않으면 Codex를 재시작하거나 새 세션을 여세요.

### 사용법

Codex에 이 skill을 명시적으로 사용하라고 요청합니다:

```text
Use $audit-ai-writing to review this draft for signs of AI writing and suggest concrete edits:

...
```

다시 쓰기 요청에서는 저자의 의도와 목소리를 최대한 유지합니다. 리뷰 요청에서는 실제로 수정할 수 있는 문제와 대체 문장을 제안합니다.

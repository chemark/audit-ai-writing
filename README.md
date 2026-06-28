# Audit AI Writing

<p align="center">
  English |
  <a href="#中文">中文</a> |
  <a href="#日本語">日本語</a> |
  <a href="#한국어">한국어</a>
</p>

<p align="center">
  <a href="https://skills.sh/chemark/audit-ai-writing">
    <img src="https://skills.sh/b/chemark/audit-ai-writing" alt="skills.sh">
  </a>
</p>

A portable agent skill for reviewing drafts for common AI-writing tells and publication-boundary leaks.

It is based on the Wikipedia field guide [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), but it is not an AI detector. The skill treats those signs as editing heuristics: it helps improve drafts, tighten claims, remove generic AI phrasing, and catch assistant/editor notes that accidentally leak into reader-facing prose.

The core instructions live in `SKILL.md`, so any agent that can read local instruction files can use it, including Codex, Claude Code, OpenCode, Kimi, Gemini, and other coding or writing agents.

## What It Checks

- Inflated or unsupported significance claims
- Generic AI vocabulary and over-smooth transitions
- Promotional tone, vague attribution, and formulaic endings
- Markdown, citation, or tool artifacts left in prose
- Publication-boundary leaks, such as instructions to the author, editor comments, or model self-talk inside the article

## Installation And Usage

**skills CLI** (recommended)
```bash
npx skills add chemark/audit-ai-writing
```

**Codex manual install**

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

Restart Codex or open a new session if the skill list does not refresh immediately.

**Other agents**

```bash
git clone https://github.com/chemark/audit-ai-writing.git
```

Point your agent at `SKILL.md` or the repository folder, then ask it to use the skill. Codex users can also say `Use $audit-ai-writing`.

```text
Use the audit-ai-writing skill in SKILL.md to review this draft for signs of AI writing and suggest concrete edits:

...
```

For rewrite requests, the skill should preserve the author's intent and voice. For review requests, it should report actionable issues and provide direct replacements.

## Development

Validate after edits:

```bash
python3 /path/to/skill-creator/scripts/quick_validate.py .
```

The repository includes:

```text
SKILL.md
agents/openai.yaml
references/signs-of-ai-writing.md
AGENTS.md
```

`AGENTS.md` is for coding agents that maintain this repository. End users can start with this README and `SKILL.md`.

## 中文

这是一个通用 agent skill，用来在文章发布前审查常见 AI 写作痕迹和发布语境污染。

它参考 Wikipedia 的 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)，但它不是 AI 检测器。它不会判断一篇文章是不是 AI 写的，而是把这些迹象当作编辑启发式：帮你删掉空泛表达、收紧事实主张、减少模板化 AI 腔，并检查“本来是助手或编辑对作者说的话”有没有误写进正文。

核心说明在 `SKILL.md`，所以任何能读取本地指令文件的 agent 都可以用，包括 Codex、Claude Code、OpenCode、Kimi、Gemini 和其他主流写作或编码 agent。

### 检查内容

- 被夸大的重要性，或没有证据支撑的宏大判断
- 常见 AI 词汇、过度顺滑的转场、公式化结尾
- 宣传腔、模糊归因、缺少具体事实的分析
- Markdown、引用、工具输出痕迹残留
- 发布语境污染，例如对作者的指令、编辑备注、模型自述混进文章

### 安装和用法

**skills CLI**（推荐）
```bash
npx skills add chemark/audit-ai-writing
```

**Codex 手动安装**

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

如果 skill 列表没有立刻刷新，重启 Codex 或开启一个新会话。

**其他 agent**

```bash
git clone https://github.com/chemark/audit-ai-writing.git
```

让 agent 读取 `SKILL.md` 或这个仓库目录，然后显式要求它使用这个 skill。Codex 用户也可以说 `Use $audit-ai-writing`。

```text
Use the audit-ai-writing skill in SKILL.md to review this draft for signs of AI writing and suggest concrete edits:

...
```

如果是改写请求，skill 会尽量保留作者原意和声音。如果是审稿请求，它会列出可执行问题和可直接替换的写法。

### 开发

修改后运行验证：

```bash
python3 /path/to/skill-creator/scripts/quick_validate.py .
```

仓库包含：

```text
SKILL.md
agents/openai.yaml
references/signs-of-ai-writing.md
AGENTS.md
```

`AGENTS.md` 是给维护这个仓库的 coding agents 使用的。终端用户可以从这个 README 和 `SKILL.md` 开始。

## 日本語

これは、公開前の原稿に含まれる典型的な AI 文章らしさや、公開文に混入した編集メモを確認するための汎用 agent skill です。

Wikipedia の [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) を参考にしていますが、AI 検出器ではありません。文章の作者を断定するものではなく、編集上のヒューリスティックとして使います。曖昧な表現、根拠の弱い主張、定型的な AI 風表現、読者向け本文に紛れ込んだアシスタントや編集者向けの発話を見つけやすくします。

中心となる手順は `SKILL.md` にあります。そのため、ローカルの指示ファイルを読める agent であれば利用できます。Codex、Claude Code、OpenCode、Kimi、Gemini などの主要な writing/coding agent で使えます。

### チェック内容

- 根拠のない大げさな重要性の主張
- AI らしい語彙、滑らかすぎる接続、定型的な結論
- 宣伝調、曖昧な帰属、具体性のない分析
- Markdown、引用、ツール出力の残骸
- 著者への指示、編集メモ、モデルの自己言及が本文に混入している箇所

### インストールと使い方

**skills CLI**（推奨）
```bash
npx skills add chemark/audit-ai-writing
```

**Codex 手動インストール**

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

skill 一覧にすぐ表示されない場合は、Codex を再起動するか新しいセッションを開いてください。

**ほかの agent**

```bash
git clone https://github.com/chemark/audit-ai-writing.git
```

`SKILL.md` またはリポジトリ全体を agent に読み込ませてから、この skill を使うよう依頼します。Codex では `Use $audit-ai-writing` と書くこともできます:

```text
Use the audit-ai-writing skill in SKILL.md to review this draft for signs of AI writing and suggest concrete edits:

...
```

リライトでは著者の意図と声をできるだけ保ちます。レビューでは、実際に直せる問題点と置き換え案を出します。

### 開発

編集後に検証します:

```bash
python3 /path/to/skill-creator/scripts/quick_validate.py .
```

このリポジトリには以下が含まれます:

```text
SKILL.md
agents/openai.yaml
references/signs-of-ai-writing.md
AGENTS.md
```

`AGENTS.md` は、このリポジトリを保守する coding agents 向けのガイドです。通常の利用者は、この README と `SKILL.md` から始められます。

## 한국어

이 범용 agent skill은 공개 전 초안에서 흔한 AI 문체의 흔적과, 독자용 본문에 섞여 들어간 편집 메모나 어시스턴트의 말을 점검하기 위한 도구입니다.

Wikipedia의 [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)을 참고하지만, AI 탐지기는 아닙니다. 글쓴이를 판정하지 않고, 편집을 위한 휴리스틱으로 사용합니다. 모호한 표현, 근거가 약한 주장, 전형적인 AI식 문장, 저자나 편집자를 향한 말이 본문에 남아 있는 문제를 찾는 데 도움을 줍니다.

핵심 지침은 `SKILL.md`에 있습니다. 따라서 로컬 지침 파일을 읽을 수 있는 agent라면 사용할 수 있습니다. Codex, Claude Code, OpenCode, Kimi, Gemini 및 다른 주요 writing/coding agent에서 활용할 수 있습니다.

### 점검 항목

- 근거 없이 과장된 중요성 주장
- AI식 어휘, 지나치게 매끄러운 전환, 공식적인 결론
- 홍보성 문체, 모호한 출처 표현, 구체성이 부족한 분석
- Markdown, 인용, 도구 출력 흔적
- 저자 지시, 편집자 메모, 모델의 자기 언급이 독자용 본문에 섞인 경우

### 설치와 사용법

**skills CLI**(권장)
```bash
npx skills add chemark/audit-ai-writing
```

**Codex 수동 설치**

```bash
git clone https://github.com/chemark/audit-ai-writing.git ~/.codex/skills/audit-ai-writing
```

skill 목록이 바로 갱신되지 않으면 Codex를 재시작하거나 새 세션을 여세요.

**다른 agent**

```bash
git clone https://github.com/chemark/audit-ai-writing.git
```

`SKILL.md` 또는 저장소 폴더를 agent가 읽게 한 뒤 이 skill을 사용하라고 요청합니다. Codex에서는 `Use $audit-ai-writing`라고 써도 됩니다:

```text
Use the audit-ai-writing skill in SKILL.md to review this draft for signs of AI writing and suggest concrete edits:

...
```

다시 쓰기 요청에서는 저자의 의도와 목소리를 최대한 유지합니다. 리뷰 요청에서는 실제로 수정할 수 있는 문제와 대체 문장을 제안합니다.

### 개발

수정 후 검증합니다:

```bash
python3 /path/to/skill-creator/scripts/quick_validate.py .
```

저장소에는 다음 파일이 포함됩니다:

```text
SKILL.md
agents/openai.yaml
references/signs-of-ai-writing.md
AGENTS.md
```

`AGENTS.md`는 이 저장소를 유지보수하는 coding agents를 위한 안내입니다. 일반 사용자는 이 README와 `SKILL.md`에서 시작하면 됩니다.

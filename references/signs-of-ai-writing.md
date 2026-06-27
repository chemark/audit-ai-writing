# Signs of AI Writing Review Checklist

Source: https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing, checked 2026-06-27. The source is a descriptive Wikipedia field guide, not a policy and not proof of AI authorship.

## Review Stance

- Treat indicators as signals to investigate, not a verdict.
- Prefer improving text quality over hiding tells.
- Be stricter about factuality, source integrity, and unsupported claims than about isolated style quirks.
- Check whether the genre naturally uses the pattern before flagging it.

## Content Signals

- Inflated significance: phrases that make ordinary facts sound historically pivotal, transformative, enduring, or part of a broad trend without evidence.
- Generic legacy framing: "serves as a testament", "underscores the importance", "reflects broader", "lasting impact", "key role", "pivotal moment".
- Superficial analysis: confident commentary that sounds plausible but adds no concrete mechanism, evidence, dates, names, tradeoffs, or causality.
- Promotional tone: breathtaking, innovative, groundbreaking, world-class, vibrant, rich tapestry, seamless blend, dynamic landscape.
- Vague attribution: "many experts say", "critics argue", "widely regarded", "observers note" without naming who, where, or why.
- Formulaic future/challenge endings: balanced paragraphs about opportunities, challenges, and future prospects that do not add new information.
- Over-explaining notability: listing media mentions or source types as proof instead of summarizing what reliable sources actually establish.

## Language Signals

- Dense AI vocabulary: delve, showcase, underscore, highlight, tapestry, realm, landscape, navigate, robust, multifaceted, testament, pivotal, crucial.
- Excessive transitions: moreover, furthermore, additionally, in conclusion, overall, it is important to note, it is worth noting.
- Negative parallelisms: "not only X but also Y", "not X but Y", "X rather than Y" used repeatedly for rhetorical polish.
- Rule of three: repeated triads of adjectives, nouns, or clauses that sound balanced but generic.
- Elegant variation: avoiding simple repeated words with awkward synonyms that reduce clarity.
- Over-smooth sentence rhythm: every paragraph has similar length, similar topic sentence, and tidy concluding flourish.

## Style And Formatting Signals

- Excessive boldface or title-case headings in ordinary prose.
- Inline-header vertical lists where prose would be clearer.
- Overuse of em dashes, especially as the default way to insert explanation or contrast.
- Curly quotes or formatting inconsistent with the surrounding document.
- Markdown artifacts in non-Markdown contexts: `**bold**`, bullets pasted into prose, stray code fences.
- Broken markup, placeholder text, or model/tool artifacts such as `turn0search0`, `contentReference`, `oaicite`, `attached_file`, fake citation markers, or malformed links.

## Audience And Publication Boundary Signals

- Author-facing instructions leaked into the article: "不要把它写成...", "你可以...", "如果你已经...", "我更想知道...", "let me know", "you should", "what would you".
- Editor or reviewer commentary left in the draft: "这句话像对作者说的", "这里需要补充", "我会把它改成", "建议改为", "we should mention".
- Model or tool self-talk: "I will revise", "I checked the draft", "I found no issues", "as an AI", "Codex/Claude can".
- Questions meant for the author instead of readers: asking what the author wants to cover, which option to choose, or whether a tool has already been connected.
- Publishing notes written as prose: reminders about scope, source gaps, word count, file state, or next editing steps that readers should not see.
- Mixed viewpoint within one paragraph: switching from reader-facing explanation to direct second-person instructions for the author or agent.

## Citations And Source Signals

- Broken external links or links that do not support the claim.
- Invalid DOI/ISBN values, unrelated DOI targets, or suspiciously complete-looking citations with missing essentials.
- Book citations without page numbers when a specific claim needs one.
- Named references declared but not used, or references used in unconventional places.
- Tracking fragments such as `utm_source=` in citations when cleaner source links are expected.

## Signs That May Point Human

- The author can explain specific editorial choices and source reasoning.
- The text contains context-specific details, uneven but purposeful structure, and claims tied to concrete evidence.
- Syntax may be idiosyncratic, compressed, or locally inconsistent in ways that reflect a real person rather than a generic average.

## Fix Patterns

- Replace grand claims with concrete facts: who did what, when, where, with what consequence.
- Name the source of opinions or remove the opinion.
- Delete generic concluding paragraphs unless they add new substance.
- Use simple verbs and nouns before ornamental phrasing.
- Keep one strong transition; remove the rest.
- Preserve voice. A good rewrite should sound clearer, not sanitized.
- For audience-boundary leaks, decide what the leaked sentence is doing before editing:
  - Delete pure editor notes, model status updates, and process chatter.
  - Convert useful author-facing instructions into reader-facing explanation.
  - Convert author questions into concrete article scenarios, or move them outside the published draft.
  - Keep the article's implied speaker consistent: the published text speaks from the author to readers, not from an assistant to the author.

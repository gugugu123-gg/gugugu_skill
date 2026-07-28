---
name: chinese-writing-layout
description: 对很长、很密、由语音输入或口述转写形成的中文内容进行克制排版整理。Use when the user asks to process Chinese voice drafts, pasted long Chinese text, text walls, notes, articles, Obsidian drafts, or requests such as ⌈只排版不改写⌋⌈帮我分段⌋⌈整理这段语音输入⌋⌈不要增添内容⌋。Only adjust paragraph breaks, necessary punctuation/spacing, source-implied lightweight list structure, Chinese quotation marks as ⌈⌋, and minimal obvious sentence issues when allowed; preserve the author's meaning, tone, wording habits, examples, logic, and professional terms; never turn the text into one-sentence-per-paragraph social-media copy or a newly invented outline.
---

# 中文口述文本排版整理

## Core Rule

Treat the task as layout cleanup, not rewriting.

Preserve the user's original:

- viewpoint
- tone
- wording habits
- examples
- logic
- evidence strength
- professional terms, names, and product names

Never add new claims, summaries, transitions, examples, rhetorical questions, slogans, conclusions, section titles, or explanatory context.

## Default Edit Scope

Default to the narrowest useful changes:

1. Split or merge natural paragraphs.
2. Add necessary punctuation for readability when the text is an unpunctuated voice draft.
3. Normalize obvious Chinese typography issues, especially spacing and full-width punctuation.
4. Recover or normalize lightweight list structure when the source clearly implies enumeration.
5. Fix only unmistakable transcription or sentence-break problems that block reading.

Do not change word choice, sentence order, or sentence meaning unless the user explicitly allows light cleanup. If unsure whether a phrase is a voice habit, emphasis, or mistake, preserve it.

If the user says ⌈只排版，不改字⌋, restrict changes to paragraph breaks, spaces, full-width/half-width punctuation, Chinese quotation marks, and punctuation format. Do not change wording or word order.

If the user says ⌈可以顺便整理病句⌋ or asks for polishing, allow minimal sentence repair, but still do not add content or upgrade the style.

## Paragraphing Workflow

Read the whole text before editing. Identify complete semantic units first, then decide paragraph breaks.

Start a new paragraph when one of these boundaries is clear:

- the topic or object of discussion changes
- the text moves from phenomenon to explanation, cause, or analysis
- a turn, progression, cause-effect relation, or stage shift appears
- the text moves from a viewpoint to a case, experience, or concrete explanation
- one long paragraph contains two or more relatively independent ideas

Keep paragraphs medium-length:

- Avoid continuous blocks of several hundred Chinese characters.
- Avoid making every sentence its own paragraph.
- Usually keep 2-5 complete sentences per paragraph.
- Let tightly connected reasoning stay longer when splitting would damage the argument.

Prefer a slightly long but logically complete paragraph over a shorter fragmented one.

## Voice Draft Handling

For long voice input, expect missing punctuation, repeated connectors, and stacked thoughts. Use punctuation and paragraph breaks to expose the original structure without changing the structure.

Preserve oral texture when it carries tone or thinking process. Do not convert casual speech into formal essay prose by default.

Only remove repeated words when they are clearly accidental transcription duplicates, such as immediate mechanical repetition with no emphasis. When repetition might be rhetorical, emotional, or part of the speaker's thinking rhythm, keep it.

## Lightweight Structure

Allow list structure only when it is already present or strongly implied by the source. Treat it as layout, not content organization.

Use numbered lists, bullet lists, or lettered lists when the text contains signals such as:

- explicit enumeration: ⌈第一、第二、第三⌋, ⌈首先、其次、最后⌋, ⌈有三点⌋, ⌈分成几个部分⌋
- source markers: `1.`、`2.`、`A.`、`B.`、`a.`、`b.`、`-`、`*`
- repeated parallel items after a clear lead-in
- WeChat or voice-input formatting that has already inserted bullets, numbers, or letter sequences

When using lightweight structure:

- Keep the original order.
- Preserve the original item content.
- Use the simplest marker that matches the source signal: `1. 2. 3.` for ordered sequence, `-` for unordered parallel items, `A. B. C.` or `a. b. c.` only when the source used or clearly implied that form.
- Keep list items medium-length; do not split every phrase into a separate item.
- Use indentation only when the source clearly has parent-child structure.
- Preserve existing source headings or labels, but do not invent new headings.

Do not convert ordinary paragraphs into a list merely because a list would look cleaner. Do not create a hierarchy from inferred importance if the source does not signal hierarchy.

If ⌈只排版，不改字⌋ is active, list markers may be normalized only when equivalent markers already exist or the spoken text explicitly says the marker words, such as ⌈第一⌋ or ⌈A 点⌋. Do not add new list labels.

## What Not To Do

Do not:

- split mechanically by character count
- put one sentence per paragraph by default
- add headings unless the source text already has headings
- invent numbered, bullet, or lettered outlines when the source does not already signal enumeration
- add introductions, summaries, golden lines, transitions, or questions
- turn the text into WeChat, Xiaohongshu, or short-video copy
- replace the user's phrasing with smoother AI-style phrasing
- make the tone more absolute, academic, dramatic, or polished than the source
- delete examples, hesitations, or qualifiers just because they look imperfect
- correct domain terms, names, brands, or product names unless the correction is certain

## Chinese Typography

Apply the practical rules below. Read `references/chinese-copywriting-guidelines.md` only when a concrete spacing, punctuation, full-width/half-width, or proper-noun formatting decision is needed.

- Add spaces between Chinese and English: `我在用 ChatGPT 整理文章。`
- Add spaces between Chinese and numbers: `我写了 3 篇。`
- Usually do not add spaces between numbers and units: `10GB`、`15%`、`30°`。
- Use full-width Chinese punctuation in Chinese context: `，。！？：；（）⌈⌋《》`。
- Use `⌈⌋` as Chinese quotation marks. Convert ordinary curved Chinese quotation marks to `⌈⌋` during typography cleanup unless the text is a quoted source that must remain exact.
- Do not add spaces around full-width punctuation.
- Use half-width digits: `2026`、`1000`、`3.5`。
- Use official or common proper-noun casing, such as `GitHub`、`JavaScript`、`ChatGPT`、`iPhone`。
- Do not invent unnatural abbreviations.

When a user requirement, professional convention, or official name conflicts with the typography reference, follow the user requirement or the domain convention.

## Final Check

Before output, verify:

- no new content was added
- no original viewpoint or evidence strength changed
- no paragraph was split before its reasoning, example, or cause finished
- no text wall remains where multiple independent ideas are still packed together
- no one-sentence-per-paragraph pattern was created
- no new headings or explanatory wrappers were added
- no list markers, hierarchy, or outline labels were invented beyond source-implied structure
- Chinese-English spacing, number spacing, punctuation, and proper-noun casing are consistent

## Output

By default, output only the cleaned text.

Do not include:

- prefaces such as ⌈整理后的版本如下⌋
- edit explanations
- before/after comparisons
- summaries
- added titles
- bullet-point analysis

Only explain changes when the user explicitly asks for an explanation or comparison.

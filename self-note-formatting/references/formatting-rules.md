# Formatting Rules

Use this file as the detailed rulebook for `$self-note-formatting`.

For Chinese prose, follow the same standard as the vault's Chinese copywriting guide: Chinese-English spacing, Chinese-number spacing, no space between numbers and units, full-width Chinese punctuation, half-width digits, correct proper-noun casing, no meaningless repeated punctuation, and mandatory corner quotes.

Core principle: make the smallest edit set that fixes formatting while preserving meaning, tone, and note structure.

## 1. Protected content

Never rewrite or reinterpret content while formatting.

Preserve exactly unless the user explicitly asks for broader edits:
- inline tags such as `#标签`
- wiki links such as `[[Note]]` and `[[Note|Label]]`
- Markdown links
- task list markers such as `- [ ]` and `- [x]`
- code fences and inline code
- tables
- callouts such as `> [!note]`
- block quotes
- frontmatter keys and values that already exist

Quote exception:
- In normal Chinese prose, always normalize quotation marks to corner quotes even during minimal formatting.
- Use `「」` for outer quotes and `『』` for nested quotes.
- Do not change quote characters inside code spans, code fences, URLs, frontmatter values, or exact quoted/source-preservation blocks when the user explicitly asks for exact source retention.

Do not:
- rename headings to improve style
- convert a working note into an article
- infer missing content
- add backlinks, related-notes sections, or new knowledge structure

## 2. Paragraph and block spacing

- Keep one blank line between paragraphs.
- Keep one blank line before and after headings when needed for readability.
- Keep one blank line before and after fenced code blocks, tables, block quotes, and callouts when Markdown would remain valid.
- Do not insert extra blank lines inside tables, callouts, or list items unless the structure already requires them.
- Avoid breaking tightly coupled list items, checklists, or log fragments just to make them look more literary.

## 3. Mixed-language spacing

Add spaces in these common cases:
- Chinese + English: `在 LeanCloud 上开发`
- Chinese + number: `这是 2026 年的计划`
- number + Chinese unit word: `3 个问题`, `2 次迭代`
- Chinese + emphasis or link when readability needs separation

Do not add spaces in these cases:
- number + Latin unit: `10Gbps`, `10TB`, `24GB`
- percentage and degree symbols: `15%`, `28℃`, `90°`, `233°`
- around full-width punctuation: `买了一部 iPhone，好开心`
- inside inline tags
- inside wiki links
- inside code spans, code fences, URLs, or frontmatter values unless the value itself is being normalized by user request

## 4. Punctuation normalization

In Chinese prose, use Chinese full-width punctuation when the sentence is primarily Chinese:
- `，` `。` `：` `；` `？` `！` `（` `）` `《` `》`
- use corner quotes as mandatory style: outer `「」`, nested `『』`
- convert straight quotes, English curly quotes, and Chinese curved quotes such as `"` `'` `“”` `‘’` to corner quotes in normal Chinese prose
- use `……` instead of repeated `...` only when it is clearly narrative prose rather than copied code or raw text
- reduce meaningless repeated punctuation to a single mark, such as `！！` -> `！` and `？？` -> `？`, unless repetition is clearly intentional in chat, dialogue, emotional expression, or literary voice
- use half-width punctuation inside complete English sentences or special English titles/names

Do not normalize punctuation inside:
- code
- tables where alignment would break
- copied commands
- URLs
- literal titles that intentionally mix punctuation styles

## 4.1 Full-width, half-width, and proper nouns

- Use half-width digits: `1000`, `2026`, `3.5`.
- Use official or common proper-noun casing when the correction is certain: `GitHub`, `JavaScript`, `ChatGPT`, `iPhone`, `Microsoft`.
- Do not create unnatural abbreviations or guess uncertain brand casing.
- If a complete English sentence appears inside Chinese prose, keep English punctuation inside that English sentence.

## 5. Headings and lists

- Preserve heading hierarchy.
- Do not promote or demote heading levels unless broken Markdown makes the note unreadable.
- Keep a blank line before a heading unless it is the first content after frontmatter.
- Keep a blank line after a heading before normal paragraph content.
- Keep list indentation stable.
- Preserve checklist state and ordering.
- Do not force blank lines between every list item unless readability or Markdown parsing requires it.

## 6. Code blocks, tables, and callouts

- Preserve fence language identifiers.
- Do not reflow code.
- Do not alter table cell meaning for alignment polish alone unless the table is clearly malformed.
- Preserve callout markers exactly.
- Keep quoted or callout content in its existing container unless formatting is invalid.

## 7. Frontmatter

- If frontmatter exists, preserve it.
- Do not reorder or expand existing frontmatter unless the user asks.
- If frontmatter is missing and the note is being saved after formatting, add:

```yaml
---
created: YYYY-MM-DD
---
```

- Put a blank line after frontmatter before the body.

## 8. Note-type guidance

### `lite/` and `insight/`

- Keep frontmatter first.
- Preserve existing section boundaries.
- Improve readability without forcing a new template.

### `drafts & doing/` and `experience/03_Projects/`

- Preserve working structure, progress logs, ad hoc headings, and checklists.
- Prefer compact cleanup over polished prose formatting.

### `experience/01_Records/`

- Preserve chronology and record sequence.
- Normalize spacing and punctuation only.

### `experience/02_People/`

- Preserve the note's existing profile structure.
- Avoid turning people notes into generic summaries.

## 9. Refusal conditions

Refuse or narrow the task when:
- the file is under `.obsidian/` or `.trash/`
- the file is under `raw/`
- the user asks for vault-wide batch formatting with no explicit target list
- the requested change is actually curation, rewriting, or knowledge extraction

## 10. Response format

After editing, summarize briefly:
- formatting changes applied
- whether frontmatter was added or preserved
- any areas that deserve a quick user check

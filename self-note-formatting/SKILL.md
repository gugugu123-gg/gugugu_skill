---
name: self-note-formatting
description: "Use this skill to format and lightly normalize explicitly specified notes in the self vault without changing meaning, tone, or note intent. Follow the vault's Chinese copywriting layout rules, including mandatory corner quotes 「」/『』 in Chinese prose. Trigger on requests such as '排版这个笔记', '整理这个 md', '规范这个 note', or '格式化 self 里的笔记', especially for files in lite/, insight/, drafts & doing/, and experience/03_Projects/."
---

# Self Note Formatting

Format one explicitly specified note in this vault with minimal edits. Normalize layout and Markdown hygiene while preserving meaning, voice, and note purpose.

Load [formatting-rules.md](references/formatting-rules.md) before editing. Keep this file short and use the reference file as the rulebook.

## When to use

Use this skill when the user wants formatting, cleanup, or light normalization for an existing note in the `self` vault.

Typical triggers:
- a note needs better spacing, paragraph breaks, or heading/list separation
- Chinese and English, Chinese and numbers, or numbers and units need spacing cleanup
- punctuation is inconsistent in a Chinese note, especially quote style
- Markdown structure is messy but the content should not be rewritten
- a note is missing frontmatter and will be saved again during formatting

Default mode is a single explicitly named note, not batch processing.

## When not to use

Do not use this skill when:
- the user wants curation, summarization, deepening, or rewriting
- the task is to rename, move, split, or merge notes
- the task is to add backlinks or related-notes sections
- the target is under `.obsidian/`, `.trash/`, or `raw/`
- the request is vague batch cleanup across the vault with no explicit targets

Use `$self-lite-curation` or `$self-deep-curation` for content restructuring. Use `$self-bidirectional-linking` only when the user explicitly wants linking work after note editing.

## Hard rules

- Preserve user meaning, tone, wording choices, and note intent.
- Preserve inline tags such as `#标签`.
- Preserve wiki links `[[...]]`, Markdown links, callouts, code fences, tables, block quotes, and task lists.
- In Chinese prose, normalize quotation marks to corner quotes: outer `「」`, nested `『』`.
- Do not auto-bold links.
- Do not add commentary, interpretation, or new sections unless they are needed for minimal structural hygiene.
- Do not rename files, move files, or change storage paths.
- Do not change chronology in daily records or project logs.
- Do not scan or edit `.obsidian/` or `.trash/`.

## Scope

Default editable targets:
- `lite/`
- `insight/`
- `drafts & doing/`
- `experience/03_Projects/`

Allow these only when the user explicitly targets them:
- `experience/01_Records/`
- `experience/02_People/`

Refuse:
- `.obsidian/`
- `.trash/`
- `raw/`

## Workflow

1. Read the target note and identify its note type and existing Markdown structures.
2. Load [formatting-rules.md](references/formatting-rules.md).
3. Decide whether the target is in scope.
4. Preserve all protected syntax and content-bearing structures before making edits.
5. Apply only minimal formatting changes:
   - paragraph and block spacing
   - heading, list, quote, callout, and code-block spacing
   - Chinese and English spacing
   - Chinese and number spacing
   - number and unit spacing according to the vault Chinese copywriting rules
   - punctuation normalization in Chinese context, including mandatory corner quotes
6. Preserve frontmatter if it already exists.
7. If frontmatter is missing and the note will be saved, add minimal frontmatter with only `created: YYYY-MM-DD`.
8. If frontmatter exists but contains fields other than `created`, reduce it to the single `created` field and move any meaningful metadata into body text only when the current task explicitly requires preserving it.
9. Apply note-type guidance:
   - `lite/` and `insight/`: keep frontmatter first and preserve existing section structure
   - `drafts & doing/` and `experience/03_Projects/`: preserve log, checklist, and work-in-progress shape
   - `experience/01_Records/`: normalize formatting only, not chronology or record structure
10. Return a short summary of what formatting changed and any places the user should spot-check.

## Output

Edit the specified note in place.

After formatting, report:
1. what kinds of formatting changes were made
2. whether frontmatter was added or preserved
3. any syntax-sensitive areas worth checking, such as tables or dense mixed-language passages

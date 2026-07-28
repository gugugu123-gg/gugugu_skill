---
name: self-note-curation
description: "Use this skill to organize source material in the self vault into a durable note with readable body text, explicit logic, evidence, concepts, and source links without inventing ideas. Use when the user asks to 整理笔记, 整理材料, 沉淀一下, 结构化整理, 从聊天/草稿/原文里整理出一篇笔记, or save organized material into 项目/不知道怎么分类就随便放了/."
---

# Self Note Curation

Organize source material into a durable note in the `self` vault.

This skill is the single structured note-curation workflow for the self vault. It keeps full structural rigor and saves curated notes into `项目/不知道怎么分类就随便放了/`.

## Core Position

Use this skill when the user wants existing material turned into a clearer saved note.

The result should:

- preserve the source meaning, stance, and voice
- make the reasoning and structure more visible
- keep useful original sentences
- expose concepts, evidence, problems, decisions, and durable items already present
- include logic-chain, evidence, ontology, first-principles, and Polanyi-style judgment-signal sections when the source supports them
- avoid adding new ideas, advice, examples, conclusions, or external theory
- save to `项目/不知道怎么分类就随便放了/` by default

## When To Use

Use this skill for:

- pasted AI chats, voice-like notes, transcripts, or messy source text
- explicit vault files that should become a clearer note
- dense notes that need structure and source-grounded analysis
- finished drafts that should keep the original body while gaining structure
- user requests such as `整理这个`, `沉淀一下`, `结构化一下`, `保存成笔记`, `把这段聊天整理成笔记`

## When Not To Use

Do not use this skill when:

- the user wants fresh writing, publishing polish, or content generation
- the user wants a professional outward expression; use `self-professional-narration`
- the user wants a simple in-place Markdown cleanup; use `self-note-formatting`
- the user wants only faithful text cleanup without saving; use `source-faithful-cleanup`
- the task requires reading `.obsidian/` or `.trash/`

## Hard Rules

- Never read `.obsidian/` or `.trash/`.
- Work only inside the `self` vault or with pasted user material.
- Only make explicit what is already present in the source.
- Preserve the original stance, language, and voice.
- Prefer direct extraction of original sentences over paraphrase.
- Do not invent concepts, claims, examples, causes, conclusions, or follow-up actions.
- Do not rewrite into generic AI prose.
- Do not infer hidden psychology.
- Use full structural care by default.
- Do not force every structure slot. If the source does not support a slot, omit it or write `源文未充分提供`.
- Avoid contrastive rewrites such as `不是 X，而是 Y` unless the source itself clearly uses that structure.
- Keep structure useful, not ceremonial.

Allowed edits:

- remove repeated meaning
- remove filler words and spoken noise
- split long blocks into paragraphs
- lightly reorder sentences or paragraphs for readability
- merge broken fragments when strictly necessary
- group existing claims into clearer sections

Forbidden edits:

- expand the source into a new article
- polish into publication copy
- turn the note into a methodology unless the source already contains a method
- replace the user's wording style with smoother but less faithful prose
- add external analysis or advice

## Workflow

1. Identify the input form:
   - explicit file path
   - pasted text
   - dialogue-like or oral source
   - already-written article or draft
2. Check boundaries:
   - refuse `.obsidian/` and `.trash/`
   - if a file path is provided, read the named file directly
   - search directly named folders first when the user gives a folder/topic
3. Decide the body mode:
   - use `## 正文` for dialogue-like, oral, or messy material
   - use `## 原文整理` for already-written drafts that should remain mostly intact
4. Extract and clean usable source sentences:
   - keep the source voice
   - remove repetition and filler
   - keep the reasoning path visible
5. Load the curation lenses from [future-frameworks.md](references/future-frameworks.md):
   - ontology lens
   - first-principles lens
   - Polanyi lens
6. Append full structure using [output-templates.md](references/output-templates.md):
   - issue essence
   - logic chain
   - support content and evidence
   - problems or constraints
   - handling path or decision tendency
   - concept breakdown
   - durable items worth preserving
   - source and related links
7. Save the note when the user asks to save or when the task clearly asks to organize material into the vault:
   - destination: `项目/不知道怎么分类就随便放了/`
   - filename: `YYYY-MM-DD_Topic.md`
   - frontmatter: exactly `created: YYYY-MM-DD`
   - do not append old processing suffixes
8. If the source came from a vault file:
   - include a source link in the new note body
   - if the source is in `raw/`, add a reciprocal processed-note link in the raw note body
9. After saving:
   - run a semantic backlink pass across the current vault search scope
   - add only strong related-note links with short reasons
   - skip weak keyword-only links

## Saving Behavior

- Default destination: `项目/不知道怎么分类就随便放了/`
- If the user only pastes text and does not clearly ask to save, return the organized note and suggest the filename.
- If the user gives a file path and asks to organize it, save the result by default.
- If a filename already exists, add a short disambiguator instead of overwriting.
- Use Markdown and include frontmatter with only `created`.
- Do not create or write to old curation folders.

## Output

Use [output-templates.md](references/output-templates.md).

Every structured section must stay grounded in the source. If something cannot be pointed back to the source, leave it out or mark it as `源文未充分提供`.

The final user-facing response should be Chinese and include the saved file path when a file was written.

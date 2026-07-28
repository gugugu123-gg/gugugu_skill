---
name: self-bidirectional-linking
description: "Use this skill to connect a newly created or updated self-vault note with source links, meaningful reciprocal wiki links, and optional day-record links. Use after saving structured notes, daily records, project notes, drafts, or self-profile updates in the self vault. For daily records, search only recently created notes for strong relationships instead of scanning the whole vault."
---

# Self Bidirectional Linking

## When to use

Use this skill after creating or updating a note that should be connected to related material in the `self` vault.

Typical triggers:
- a new structured note has been saved in `项目/不知道怎么分类就随便放了/`
- a new daily record has been saved in `experience/01_Records/`
- a self-model document in `self-profile/` has been updated
- a project note has been added or updated in `项目/`
- a working log in `drafts & doing/` should link to related thinking or project notes
- a curated note was derived from a file in `raw/` and needs source traceability

Use this skill after curation, not instead of curation.

## When not to use

Do not use this skill when:
- the target note is still raw and unprocessed
- the relationship is weak or only keyword-level
- the task is to rewrite the body for style
- the task requires scanning `.obsidian/` or `.trash/`

## Hard rules

- Only add links when the relationship is meaningful and explainable.
- Update both sides when creating a relationship.
- Add a short reason for the relationship on both notes.
- Treat source links, semantic links, and day links as different link types.
- Source links from `raw/` to processed notes are mandatory when a processed note comes from a raw file.
- `self-profile/` is a special case: other notes may link to notes inside `self-profile/`, but notes inside `self-profile/` must not proactively add outbound semantic links.
- When a `self-profile/` note has a fixed `Related Notes` block defined by vault rules, do not append semantic backlinks there.
- Place links inline when they directly support a passage. Otherwise place them near the end in a related-notes section.
- Prefer a small number of strong links over many weak ones.
- Do not force a backlink just because two notes share one word.
- Never read `.obsidian/` or `.trash/`.
- Default semantic search scope:
  - `项目/`
  - `raw/`
  - `咕咕咕/`
  - `self-profile/`
  - `drafts & doing/`
  - `experience/02_People/`
  - `播客/`
  - `理论知识AI总结/`
  - `摘录短文/`
  - `已发布/`
  - `优质中长文/`
  - `AAAA/`
  - `有趣的东西/`
  - `赵哥/`
- For daily records, do not scan the full semantic scope. Use daily-record mode.
- `experience/01_Records/` is optional for normal semantic search unless the user asks for it or the target note is a daily record.
- `self-profile/` does not use day links.

## Daily-Record Mode

Use this mode automatically when the target note is under `experience/01_Records/`.

Discovery rules:

- Do not read the whole vault.
- Use the daily record date as the anchor date.
- Default recent window: the anchor date and the previous 7 days.
- Candidate folders:
  - `项目/`
  - `raw/`
  - `drafts & doing/`
  - `咕咕咕/`
  - `播客/`
  - `理论知识AI总结/`
  - `摘录短文/`
  - `优质中长文/`
  - `已发布/`
  - `AAAA/`
  - `有趣的东西/`
  - `赵哥/`
  - `self-profile/`
- Skip `.obsidian/`, `.trash/`, `.agents/`, `.claude/`, `图片/`, and `Excalidraw/` unless the daily record explicitly mentions a visual file.
- Determine recency in this order:
  1. `created` frontmatter date
  2. date in filename or parent folder
  3. file modification time
- Read only candidate files in the recent window, then apply [linking-criteria.md](references/linking-criteria.md).
- Compare candidates against `经历`, `想法`, `灵感与线索`, and `推理或思路`.
- Add at most 5 semantic links unless the user explicitly asks for broader linking.
- If no strong related notes exist, add nothing.

## Workflow

1. Read the target note and identify:
   - core topic
   - related projects
   - recurring concepts
   - named people, systems, or objects
   - direct references worth linking
2. Determine link types with [link-types.md](references/link-types.md):
   - source links
   - semantic links
   - day links
3. If the note was processed from `raw/`, add a source link on the processed note and a reciprocal processed-note entry on the raw note, both in body text or end sections, never in frontmatter.
4. Search for related notes:
   - if the target is a daily record, use Daily-Record Mode
   - otherwise search the default semantic scope
   - only include `experience/01_Records/` in normal semantic search when the user asks for it
5. Use the selection rules in [linking-criteria.md](references/linking-criteria.md) to keep only strong semantic candidates.
6. Decide placement with [placement-rules.md](references/placement-rules.md):
   - inline when a nearby claim clearly benefits from the link
   - end-of-note when the relationship is general rather than local
7. Add the semantic wiki link plus a short relevance reason in the target note.
8. Update the related note with a reciprocal wiki link plus a matching reason.
   - Exception: if the related note is in `self-profile/`, do not add the reciprocal semantic link unless the user explicitly asks for it.
9. If a same-day record exists in `experience/01_Records/`, optionally add a day link instead of creating broad same-day note-to-note links. Skip day links for notes in `self-profile/`.
10. If no strong semantic candidates exist, leave the note semantically unlinked rather than inventing a weak graph.

## Output

This skill edits notes in place.

When adding a related-notes block, use a compact style such as:
- `- [[Related Note]]: shares the same project constraint`
- `- [[Related Note]]: expands the decision logic behind this note`

When adding a source block, use a compact style such as:
- `- Source: [[raw/...]]`

When adding a day-record block, use a compact style such as:
- `- Day Record: [[experience/01_Records/YYYY-MM-DD]]`

When adding inline links, keep the local sentence readable and add only the shortest useful reason nearby.

## Saving behavior

- Do not create new top-level notes just for linking.
- Preserve existing frontmatter.
- Frontmatter for notes in this vault should stay limited to `created`.
- If a related-notes section already exists, append to it instead of duplicating it.
- If no suitable placement exists, create a concise related-notes section near the end.
- If a processed-notes section already exists on a raw note, append to it instead of duplicating it.

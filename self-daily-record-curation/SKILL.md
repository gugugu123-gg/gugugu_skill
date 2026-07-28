---
name: self-daily-record-curation
description: "Use this skill to curate messy daily material in the self vault into a structured day record under `experience/01_Records/`. Use for pasted logs, chats, voice-like notes, or raw daily source files that should become `今日状态 / 经历 / 想法 / 灵感与线索 / 推理或思路 / 证据与来源` without invented content, while allowing a small source-grounded read on the user's mood or how the day felt."
---

# Self Daily Record Curation

## When to use

Use this skill when the user wants daily material turned into a clean day record.

Typical triggers:
- a raw daily note is messy and should be organized into one record
- pasted text contains the day's events, decisions, and scattered thoughts
- voice-like or dialogue-like material should become a usable day record

## When not to use

Do not use this skill when:
- the user wants a durable topic note rather than a daily record; use `self-note-curation`
- the user wants philosophical distillation, project synthesis, or self-model extraction
- the task requires reading `.obsidian/` or `.trash/`

## Hard rules

- Only organize what the source already says.
- Do not summarize upward into lessons, methods, or personality traits.
- Do not invent events, motives, or conclusions.
- `今日状态` is optional, lightweight, and for fun. It may briefly describe the user's visible mood, rhythm, or how the day seems to have gone, but only when the source gives concrete support.
- Do not turn `今日状态` into psychoanalysis, personality judgment, or motivational commentary.
- If the source does not support a mood/state read, write `- 源文未明确显示`.
- Remove repeated filler, spoken noise, and obvious duplication when needed.
- Keep the user's wording and concrete details whenever possible.
- Do not append the full original material at the end of the record by default.
- Keep only the structured daily record plus concise source notes or source links when useful.
- Separate `今日状态`, `经历`, `想法`, `灵感与线索`, and `推理或思路` only when the source supports the split.
- Keep `想法` as the place for the user's articulated views, judgments, takeaways, and summarized thoughts from the day.
- Use `灵感与线索` as a separate capture layer for idea seeds, writing material, research directions, future-use signals, and promising fragments that should not get buried.
- If the source does not make a thought path clear, write `- 源文未明确展开`.
- Every section should remain traceable to the source.
- In `灵感与线索`, actively look for statements such as "I want to write", "this is good material", "I should study this", "this could become a skill/project/article", or equivalent signals of future use.
- In `灵感与线索`, it is allowed to infer a likely writing topic, research direction, or latent intention only when the source gives concrete support; keep such wording conservative.
- Only include full original material if the user explicitly asks for full source retention in the saved record.
- Never read `.obsidian/` or `.trash/`.
- After saving a daily record, automatically run `$self-bidirectional-linking` in daily-record mode.
- Daily-record linking must look for related notes in the vault, but it must not read the whole vault. Limit discovery to notes created in the last 7 days relative to the record date, plus clearly same-day notes.
- Prefer `created` frontmatter for recency. If missing, use a filename date. If both are missing, use file modification time as a fallback.
- Only add strong related-note links. Do not create links just because notes are near in time.

## Workflow

1. Identify the input form:
   - explicit file path
   - pasted daily material
2. Check that the source is inside allowed vault directories.
3. Read the material and extract:
   - the visible tone, mood, energy, or how the day appears to have felt
   - what happened
   - what was thought, judged, or decided
   - any visible reasoning or thought path
   - any idea seeds, promising phrasing, writing intentions, research intentions, topic candidates, or explicit mentions of "record this", "write this", "study this", "this is a good angle", or similar
4. Remove repeated filler and spoken noise only as needed for the structured sections.
5. Organize the result with the template in [output-template.md](references/output-template.md).
   - keep `今日状态 / 经历 / 想法 / 灵感与线索 / 推理或思路 / 证据与来源` concise and source-faithful
   - use `今日状态` for a brief, source-grounded read such as the day's overall rhythm, emotional color, or whether the day felt smooth, tense, scattered, heavy, energized, etc.
   - keep `今日状态` playful but restrained; one to three bullets is enough
   - if the source only supports a partial read, describe only that partial read
   - keep `想法` focused on the user's expressed thoughts, judgments, and summarized understanding
   - use `灵感与线索` to surface good thoughts, usable angles, topic seeds, possible writing material, possible research directions, and explicit future-intent signals
   - if the source contains only a fragment but it clearly points toward a topic or direction, capture that in `灵感与线索` with cautious wording
   - do not fabricate a project, article, or research direction when the source does not support it
   - do not append a final raw-material section unless the user explicitly requests it
6. Saving behavior:
   - if the user gives a file path, write to `experience/01_Records/YYYY-MM-DD.md`
   - if the user only pastes text, return the result and a suggested filename without writing
7. When saving:
   - add frontmatter with exactly one field: `created: YYYY-MM-DD`
   - keep the filename exactly `YYYY-MM-DD.md`
8. If the note came from `raw/`, add a source link and ensure the raw note gets a reciprocal processed-note entry in body text or an end section, not in frontmatter.
9. After saving a new record, run `$self-bidirectional-linking` in daily-record mode:
   - target note: `experience/01_Records/YYYY-MM-DD.md`
   - recent window: the record date and the previous 7 days
   - candidate sources: current vault content folders, excluding `.obsidian/`, `.trash/`, `.agents/`, `.claude/`, `图片/`, and `Excalidraw/` unless the record explicitly mentions a visual artifact
   - compare candidates against `经历 / 想法 / 灵感与线索 / 推理或思路`
   - add only meaningful semantic links with short reasons
   - update reciprocal links on related notes unless the related note is in `self-profile/`
   - if no strong candidates exist, leave the record unlinked rather than forcing weak links

## Output

Use the template in [output-template.md](references/output-template.md).

This skill produces a daily record, not a topic essay and not an insight note.
The final note should not repeat the full input text at the end by default.
Within that constraint, `今日状态` can add a small amount of fun and readability when the source supports it, `灵感与线索` should be handled with extra care because daily records are also a place to rescue valuable fragmented ideas before they disappear, and `想法` should remain the user's clearer thought layer.

## Saving behavior

- Default destination: `experience/01_Records/`
- File name: `YYYY-MM-DD.md`
- If the source is pasted text, return the note content plus a suggested date filename.

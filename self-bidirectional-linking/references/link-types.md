# Link Types

Use three link types and keep them separate.

## Source Links

Use when:
- a structured note was processed from a file in `raw/`

Rules:
- source links are mandatory
- the processed note should point back to the raw note
- the raw note should list the processed note in a processed-notes section

## Semantic Links

Use when:
- two notes are meaningfully related by topic, project, problem, continuation, or evidence

Rules:
- use the default semantic search scope
- add reciprocal links with short reasons
- prefer a few strong links over many weak ones
- `self-profile/` participates in semantic linking by default

## Day Links

Use when:
- a same-day record exists in `experience/01_Records/`
- the note clearly belongs to that day's activity context

Rules:
- day links are lighter than semantic links
- prefer linking to the day record over creating many weak same-day links between notes
- do not turn all notes from the same date into a complete mesh
- do not use day links for `self-profile/` because it is versioned rather than daily

## Daily Record Semantic Links

Use when:
- the target note is itself a daily record
- recently created notes share a meaningful event, idea, project, person, constraint, or reasoning path with the record

Rules:
- search only the recent window defined in `SKILL.md`
- do not read the whole vault
- add reciprocal semantic links for strong matches
- prefer no links over weak time-neighbor links

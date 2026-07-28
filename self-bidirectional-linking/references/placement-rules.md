# Placement Rules

Use inline placement when:

- a specific sentence or paragraph mentions a concept, project, or decision that another note directly expands
- the reader benefits from jumping at that exact point

Use end-of-note placement when:

- the relationship is broad rather than tied to one sentence
- there are several related notes
- inline insertion would interrupt readability

Recommended end section:

```md
## Related Notes
- [[Note A]]: short reason
- [[Note B]]: short reason
```

Recommended source section:

```md
## Source
- [[raw/path-to-note]]: source material for this processed note
```

Recommended processed-notes section on raw notes:

```md
## Processed Notes
- [[项目/不知道怎么分类就随便放了/YYYY-MM-DD_Topic]]: structured note curated from this source
```

Recommended day-link section:

```md
## Day Context
- [[experience/01_Records/YYYY-MM-DD]]: same-day record
```

Do not add a day-context section to files under `self-profile/`.

For daily records, prefer an end section:

```md
## Related Notes
- [[Related Note]]: same project, idea, or reasoning path appearing in this day record
```

Reciprocal rule:

- every added relationship must be written back to the related note
- the reverse-side reason can be shorter, but it must still explain the connection

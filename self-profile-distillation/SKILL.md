---
name: self-profile-distillation
description: "Use this skill to distill stable self-model patterns from the self vault across a chosen time range into the self-profile layer. Best for low-frequency updates based on lite, insight, experience, and drafts rather than daily note processing."
---

# Self Profile Distillation

## When to use

Use this skill when the user wants to update the `self-profile/` layer from a meaningful body of material across time.

Typical triggers:
- the user wants a new self-profile pass for a time range such as one week, one month, or a project phase
- there is enough accumulated content in `lite/`, `insight/`, `experience/`, and `drafts & doing/`
- the user wants to update the stable self-model rather than process one raw note
- the user wants to add one or more explicit notes as supplementary evidence on top of the time-range scan

This skill is low-frequency. It is not part of the daily `raw -> lite -> insight` pipeline.

## When not to use

Do not use this skill when:
- the user wants to process one raw input into `lite/` or `insight/`
- the user wants style editing, article rewriting, or publishing output
- there is too little material to support stable pattern extraction
- the task is to scan `.obsidian/` or `.trash/`

## Hard rules

- Distill only long-running, repeated, cross-note patterns.
- Do not upgrade one isolated note into a stable self-model trait.
- Do not invent personality claims, motives, or psychological diagnoses.
- Do not turn this layer into a resume generator, evaluation report, or inspirational summary.
- Read notes in time order using `created` where available.
- If a note lacks `created`, skip it or explicitly mark it as incomplete evidence.
- Default source scope:
  - `lite/`
  - `insight/`
  - `experience/01_Records/`
  - `experience/02_People/`
  - `experience/03_Projects/`
  - `drafts & doing/`
- `raw/` is not a default source. Include it only when the user explicitly requests it.
- Update the stable files in `self-profile/` in place. Do not create a new version file for every run.
- If version, last-updated, source-range, or module markers are needed, write them in the body text, not frontmatter.

## Workflow

1. Determine the source window:
   - required date range
   - optional explicit supplemental notes
2. Read the selection rules from [source-selection.md](references/source-selection.md).
3. Gather notes from the default source scope inside the requested date range.
4. Sort candidate notes by `created`.
5. Exclude or flag notes with missing `created` according to [source-selection.md](references/source-selection.md).
6. Distill stable patterns into five persistent files using [module-guide.md](references/module-guide.md) and [output-templates.md](references/output-templates.md):
   - `00_Self Profile.md`
   - module 01
   - module 02
   - module 03
   - module 04
7. Keep every high-level judgment grounded in multiple pieces of evidence where possible.
8. Update version or last-updated information in the body only when there is a clear model shift or a meaningful refresh.
9. After updating `self-profile/`, run `$self-bidirectional-linking` so the profile layer joins the vault graph.

## Output

This skill updates the stable `self-profile/` files in place.

The layer contains:
- one overview file
- four module files

Required frontmatter for every file:
- `created`

If the overview needs version, last-updated, or source-range information, keep it in body sections rather than frontmatter.

If a module page needs a module identifier or update marker, keep it in body sections rather than frontmatter.

Use the exact structures in [output-templates.md](references/output-templates.md).

## Saving behavior

- Save only under `self-profile/`
- Preserve frontmatter and existing links where possible
- Do not create daily folders for `self-profile/`
- Keep the layer versioned through body text and stable filenames, not through extra frontmatter fields or proliferating filenames

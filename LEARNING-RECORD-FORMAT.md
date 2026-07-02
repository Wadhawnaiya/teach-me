# Learning Record Format

Learning records are the most valuable signal in the workspace. They live in `./learning-records/` as `0001-slug.md`, `0002-slug.md`, etc. (increment from the highest existing number). Create the folder only when the first one is written.

They are the teaching equivalent of high-signal ADRs: they capture non-obvious, decision-relevant insights that change what should be taught next and protect against re-teaching or over-teaching.

## Template (Keep It Short)

```md
# {Short, descriptive title of what was established or corrected}

{1-4 sentences: What the user now understands or demonstrated, the evidence, why it matters for future teaching, and any implications for mission or technique.}

**Evidence**: (optional but powerful)
- Specific question answered correctly in own words
- Exercise / Feynman explanation / real-world micro-action completed
- Prior knowledge disclosed with accurate depth

**Techniques used**: active recall, Feynman, interleaving, etc. (optional)

**Next review cue**: (for spaced repetition planning)
```

Status frontmatter (rarely needed):

```yaml
---
status: active | superseded by LR-00XX
---
```

## When to Write One (High Bar)

Write a record only when one or more is true:

1. The user demonstrated **genuine, usable understanding** of something non-trivial (not just exposure or recognition).
2. The user disclosed **prior knowledge** ("I already know...") — record the claimed depth so we never re-teach at the wrong level.
3. A **misconception was corrected** with clear before/after. These are gold for future prediction.
4. The **mission meaningfully shifted** in response to what was learned. Cross-reference MISSION.md.

### Red Flags — Do NOT Write
- Material merely covered or explained by you.
- Surface-level questions answered.
- Anything already captured tersely and accurately in the GLOSSARY.
- Daily activity logs or "we covered X today".

**Common rationalization**: "This feels important." → Only decision-grade insights that will change future teaching belong here.

## Supersession

If a later record shows an earlier understanding was incomplete or wrong, mark the old record:

```
---
status: superseded by LR-0042
---
```

Keep the history. The evolution of understanding is itself valuable data.

## Numbering & Hygiene

- Scan the directory for the highest number. Next is +1. Zero-pad to 4 digits.
- Filenames are `NNNN-kebab-case-short-title.md`.
- Records are decision-grade, not prose. Short is better.

These records are how you (the teacher) actually know where the learner truly is.

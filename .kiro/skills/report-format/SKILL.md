---
name: report-format
description: The structure, scoring and wording for the review report written to reviews/. Use when writing the final report.
---

# Report format

## Scoring

- Met = 2, Partly = 1, Missing = 0, N/A = excluded
- Score per criterion = points × criterion weight
- Overall % = total scored ÷ total possible (in-scope criteria only), rounded to whole number
- Activity RAG: Green ≥ 80%, Amber 50–79%, Red < 50%

## Verdict

- **Fit for purpose** – overall ≥ 80% and no High priority gaps
- **Fit for purpose with changes** – overall 50–79%, or ≥ 80% with one or more High gaps
- **Not yet fit for purpose** – overall < 50%, or three or more High gaps

## Template

Use exactly this structure. Keep each section tight.

```markdown
# ITIL 5 Review: <document title>

**Reviewed:** <YYYY-MM-DD> · **File:** <path> · **Rubric version:** <version from rubric file>

## Verdict

**<Verdict>** – <overall %>

<Two or three sentences: what the document does well and the main thing holding it back.>

## Classification

- **Document type:** …
- **Primary activities:** …
- **Secondary activities:** …
- **Confidence:** …

## Scores by activity

| Activity | Score | RAG |
|---|---|---|
| … | …% | 🟢/🟠/🔴 |
| Cross-cutting | …% | … |

## Top 5 gaps

1. **<criterion ID> – <short name>** (High/Medium/Low)
   What's missing: …
   Suggested fix: …

## All findings

| ID | Criterion | Result | Evidence / location | Priority | Suggested fix |
|---|---|---|---|---|---|
| … | … | Met/Partly/Missing/N/A | … | … | … |

## Questions for the author

- <3–6 questions that would close the biggest gaps>

## General observations

- <Anything worth saying that is not an ITIL criterion. Label clearly. Optional.>

## Review notes

- Knowledge base used: Yes/No
- Limitations: <e.g. images not read, document truncated, classification low confidence>
```

## Wording

- Plain and direct. No "it is recommended that". Say "Add…", "State…", "Name…".
- Suggested fixes should be wording the author could paste and adapt.
- Quotes from the document under 15 words.

---
name: report-format
description: The structure, scoring and wording for the review report written to reviews/, shared by the ITIL and SIAM reviewers. Use when writing the final report.
---

# Report format

Used by both reviewers. Where the template says **<Framework>**, write `ITIL 5` or `SIAM`. Where it says **area**, the ITIL reviewer uses lifecycle activities (discover, design …) and the SIAM reviewer uses rubric areas (Layers and roles, Governance …).

## Scoring

- Met = 2, Partly = 1, Missing = 0, N/A = excluded
- Score per criterion = points × criterion weight
- Overall % = total scored ÷ total possible (in-scope criteria only), rounded to whole number
- Area RAG: Green ≥ 80%, Amber 50–79%, Red < 50%

## Verdict

- **Fit for purpose** – overall ≥ 80% and no High priority gaps
- **Fit for purpose with changes** – overall 50–79%, or ≥ 80% with one or more High gaps
- **Not yet fit for purpose** – overall < 50%, or three or more High gaps

## Template

Use exactly this structure. Keep each section tight.

```markdown
# <Framework> Review: <document title>

**Reviewed:** <YYYY-MM-DD> · **File:** <path> · **Rubric:** <rubric file name> v<version>

## Verdict

**<Verdict>** – <overall %>

<Two or three sentences: what the document does well and the main thing holding it back.>

## Classification

<Use the classification lines from your classification skill.>

## Scores by area

| Area | Score | RAG |
|---|---|---|
| … | …% | 🟢/🟠/🔴 |

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

- <Anything worth saying that is not a rubric criterion. Label clearly. Optional.>
- <If the other reviewer would add value, say so here, e.g. "Several providers involved – run siam-reviewer as well".>

## Review notes

- Knowledge base used: Yes/No
- Limitations: <e.g. images not read, document truncated, classification low confidence>
```

## Wording

- Plain and direct. No "it is recommended that". Say "Add…", "State…", "Name…".
- Suggested fixes should be wording the author could paste and adapt.
- Quotes from the document under 15 words.

# Review agents – Claude Code use

This repo is built for Kiro CLI (`.kiro/`), but the agents can be tested in Claude Code on the Mac.

## Which agent

- "review …" or "ITIL review …" → ITIL reviewer
- "SIAM review …" → SIAM reviewer
- "model …" → value modeller (`.kiro/prompts/itil5-value-modeller.md`)

## ITIL review

1. Read `.kiro/prompts/itil5-reviewer.md` and follow it exactly.
2. Read `rubric/itil5-product-rubric.yaml`, `.kiro/steering/org-context.md`, and the skills `itil-doc-classification`, `itil-cross-cutting` and `report-format` in `.kiro/skills/`.
3. If `kb/` holds files other than `README.md`, search them to confirm criteria.

## SIAM review

1. Read `.kiro/prompts/siam-reviewer.md` and follow it exactly.
2. Read `rubric/siam-rubric.yaml`, `.kiro/steering/org-context.md`, and the skills `siam-doc-classification`, `siam-checks` and `report-format` in `.kiro/skills/`.
3. If `kb-siam/` holds files other than `README.md`, search them to confirm criteria.

## Both

- Write reports only to `reviews/`. Never edit files in `inbox/`, `rubric/`, `kb/`, `kb-siam/` or `.kiro/` during a review.
- When asked to change an agent (rubric, prompt, skills), edit those files directly and keep its Kiro config in `.kiro/agents/` in step.

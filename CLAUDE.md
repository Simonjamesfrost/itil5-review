# ITIL 5 review agent – Claude Code use

This repo is built for Kiro CLI (`.kiro/`), but can be tested in Claude Code on the Mac.

When asked to review a document:

1. Read `.kiro/prompts/itil5-reviewer.md` and follow it exactly.
2. Read `rubric/itil5-product-rubric.yaml`, `.kiro/steering/org-context.md` and the three skills in `.kiro/skills/`.
3. If `kb/` holds files other than `README.md`, search them to confirm criteria.
4. Write the report only to `reviews/`. Never edit files in `inbox/`, `rubric/`, `kb/` or `.kiro/`.

When asked to change the agent itself (rubric, prompt, skills), edit those files directly and keep the Kiro config in `.kiro/agents/itil5-reviewer.json` in step.

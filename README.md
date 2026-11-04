# ITIL 5 Document Review Agent

A Kiro CLI agent that reviews documents against ITIL (Version 5) Product guidance and writes a scored findings report.

## What's in here

```
.kiro/
  agents/itil5-reviewer.json   Kiro agent config
  prompts/itil5-reviewer.md    system prompt – how the agent reviews
  steering/org-context.md      your organisation's terms and house rules – edit this
  skills/
    doc-classification/        works out document type and lifecycle activities
    cross-cutting/             guiding principles, four dimensions, governance, AI
    report-format/             scoring, verdict and report template
rubric/itil5-product-rubric.yaml   59 review criteria – the core asset
kb/                            licensed ITIL text, local only (gitignored)
inbox/                         documents to review (gitignored)
reviews/                       reports written here (gitignored)
samples/sample-release-plan.md test document
CLAUDE.md                      lets you test the same agent in Claude Code
```

## Moving it to the work machine

**On the Mac (once):**

```bash
cd itil5-review
git init -b main          # skip if already a repo
git add .
git commit -m "ITIL 5 review agent v0.1"
gh repo create itil5-review --private --source . --push
# or create an empty private repo on github.com and:
# git remote add origin https://github.com/<you>/itil5-review.git
# git push -u origin main
```

**On the work machine:**

```bash
git clone https://github.com/<you>/itil5-review.git
cd itil5-review
```

Later updates: `git pull` on the work machine after you push from the Mac.

`kb/`, `inbox/` and `reviews/` never go to GitHub. Copy licensed ITIL text into `kb/` on each machine by hand.

## Running it in Kiro CLI

Always run from the repo root – the resource paths are relative to it.

```bash
cd itil5-review
kiro-cli --agent itil5-reviewer
```

Then:

```
review samples/sample-release-plan.md
```

The report lands in `reviews/`. Put real documents in `inbox/` as Markdown or text. Convert Word or PDF first (Save As → Plain Text, or paste into a `.md` file).

If the agent doesn't appear in `/agent swap`, run `/upgrade-agent diagnostics` – Kiro will say which field it doesn't like.

## Testing in Claude Code on the Mac

```bash
cd itil5-review
claude
> review samples/sample-release-plan.md
```

`CLAUDE.md` points Claude Code at the same prompt, rubric and skills, so results should be close to Kiro's.

## Before using on work documents

- Check Kiro is approved for the kind of data in the document. Document content is sent to the model provider.
- Check the rubric: criteria marked `verified: false` have not yet been checked against the ITIL Product (Version 5) source.

## Next steps

1. Run the sample and check the report reads well.
2. Verify rubric criteria against ITIL Product (Version 5) and set `verified: true`.
3. Fill in `.kiro/steering/org-context.md`.
4. Try 3 real documents and compare with your own review. Tune weights and wording.

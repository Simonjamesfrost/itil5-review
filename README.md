# Document Review Agents – ITIL 5 and SIAM

Kiro CLI agents that review documents and write scored findings reports.

| Agent | Looks at | Start with |
|---|---|---|
| `itil5-reviewer` | One product or service across the ITIL (Version 5) lifecycle | `kiro-cli --agent itil5-reviewer` |
| `siam-reviewer` | How several providers, a service integrator and the customer work together (SIAM) | `kiro-cli --agent siam-reviewer` |
| `itil5-value-modeller` | Builds a value model and diagrams for a service (see below) | `kiro-cli --agent itil5-value-modeller` |

Not sure which reviewer? If the document involves two or more suppliers or teams handing work between them, run both. Each reviewer flags when the other would add something.

**New here? Start with [HOWTO.md](HOWTO.md)** – setting up on the work machine, running a review, and getting updates.

## What's in here

```
.kiro/
  agents/
    itil5-reviewer.json          ITIL reviewer config
    siam-reviewer.json           SIAM reviewer config
    itil5-value-modeller.json    value modeller config
  prompts/                       system prompts – how each agent works
  steering/org-context.md        your organisation's terms and house rules – edit this
  skills/
    itil-doc-classification/     ITIL: document type and lifecycle activities
    itil-cross-cutting/          ITIL: guiding principles, four dimensions, governance, AI
    siam-doc-classification/     SIAM: document type, perspective, roadmap stage, areas
    siam-checks/                 SIAM: how to judge each area, failure patterns
    report-format/               shared: scoring, verdict and report template
    value-model/, diagram-standards/   value modeller
rubric/
  itil5-product-rubric.yaml      59 ITIL criteria
  siam-rubric.yaml               67 SIAM criteria across 11 areas
kb/                              licensed ITIL text, local only (gitignored)
kb-siam/                         SIAM guidance text, local only (gitignored)
inbox/                           documents to review (gitignored)
reviews/                         reports written here (gitignored)
samples/
  sample-release-plan.md         ITIL test document
  sample-major-incident-procedure.md   SIAM test document (three suppliers)
CLAUDE.md                        lets you test the agents in Claude Code
```

## SIAM reviewer (v0.1)

Reviews a document from the multi-provider point of view. It works out whose perspective the document is written from (customer, service integrator or provider), which SIAM roadmap stage it belongs to, and which areas apply. Then it checks accountability across all parties, joined-up processes, contracts, data ownership, end-to-end measures, collaboration and transitions. It also looks for common failure patterns, such as tickets being passed between suppliers, or every supplier reporting green while the end-to-end service is red.

```bash
kiro-cli --agent siam-reviewer
> review samples/sample-major-incident-procedure.md
```

The rubric is written from the SIAM Professional Body of Knowledge (2nd edition, 2019) and SIAM Process Guides (2nd edition, 2020). It has not yet been checked against the 2025 SIAM BoK refresh. Download the guidance into `kb-siam/` – see `kb-siam/README.md`.

## Value modeller (v0.2)

A second agent, `itil5-value-modeller`, builds a value creation model and Mermaid diagrams for a service instead of scoring a document.

```bash
kiro-cli --agent itil5-value-modeller
> model <path to source file>
```

Output goes to `C:\Users\sfrost\Downloads\` as `<service-name>-value-model-<date>.md` — a working location. Copy the finished model into the relevant project folder once the content is agreed (consumer outcomes are drafted as "Unconfirmed" until you confirm them). Files: `.kiro/agents/itil5-value-modeller.json`, `.kiro/prompts/itil5-value-modeller.md`, and the skills `value-model` and `diagram-standards`.

> The output path `C:\Users\sfrost\Downloads\` is hard-coded in the agent config and prompt for this machine. On a different machine or user, edit the `fs_write` rule and the save path in `.kiro/prompts/itil5-value-modeller.md` to your own working folder.

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

`kb/`, `kb-siam/`, `inbox/` and `reviews/` never go to GitHub. Copy licensed ITIL text into `kb/` and SIAM guidance into `kb-siam/` on each machine by hand.

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
- Check the rubrics: criteria marked `verified: false` have not yet been checked against the source. For SIAM, `verified: true` means checked against the 2019/2020 editions only.

## Next steps

1. Run both samples and check the reports read well.
2. Verify rubric criteria against ITIL Product (Version 5) and the 2025 SIAM BoK refresh, and set `verified: true`.
3. Fill in `.kiro/steering/org-context.md`.
4. Try 3 real documents and compare with your own review. Tune weights and wording.

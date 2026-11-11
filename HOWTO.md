# How to set up and use the review agents

Two reviewers share this repo:

- `itil5-reviewer` – one product or service across the ITIL lifecycle
- `siam-reviewer` – how several suppliers, a service integrator and the customer work together

The steps are the same for both – just swap the agent name.

## 1. Get it onto the work machine (first time)

The repo is private, so Git will ask you to sign in to GitHub the first time.

```bash
git clone https://github.com/Simonjamesfrost/itil5-review.git
cd itil5-review
```

If Git asks for a password, use a GitHub personal access token, not your GitHub password:
github.com → Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token. Give it access to `itil5-review` only, with **Contents: Read-only**. Paste the token when Git asks for the password.

## 2. Check it runs

Always start Kiro from inside the `itil5-review` folder – the agent's file paths are relative to it.

```bash
cd itil5-review
kiro-cli --agent itil5-reviewer
```

Then type:

```
review samples/sample-release-plan.md
```

You should get a short verdict in the chat and a full report in `reviews/`. The sample has deliberate gaps (no rollback plan, no support handover, single approver), so it should come out as *Fit for purpose with changes* or *Not yet fit for purpose*.

For the SIAM reviewer:

```bash
kiro-cli --agent siam-reviewer
```

```
review samples/sample-major-incident-procedure.md
```

That sample has three suppliers each working to their own target, tickets passed between them, no end-to-end target and no shared priority model. It should come out as *Not yet fit for purpose*.

If an agent isn't found or Kiro complains about the config, run `/upgrade-agent diagnostics` inside Kiro – it will name the field it doesn't like.

## 3. Review a real document

1. Save the document as Markdown (`.md`) or plain text (`.txt`).
   - Word: File → Save As → Plain Text.
   - Confluence: copy the page into a new `.md` file.
   - PDF: copy the text into a `.md` file.
2. Put it in `inbox/`.
3. In Kiro: `review inbox/<file name>`
4. Open the report in `reviews/`. SIAM reports end in `-siam-review-<date>.md`, so the two never overwrite each other.

`inbox/` and `reviews/` are never pushed to GitHub, so company documents stay on the machine.

Before reviewing work documents, check Kiro is approved for that kind of data – the document content is sent to the model provider.

## 4. Get updates

When you change the agent on the Mac and push, update the work machine with:

```bash
cd itil5-review
git pull
```

## 5. Add ITIL source text (optional)

If you have licensed ITIL (Version 5) text, for example from PeopleCert Plus:

1. Save it as Markdown or text files in `kb/` – one file per lifecycle activity works well.
2. Restart Kiro. It indexes `kb/` when the agent starts.

`kb/` is never pushed to GitHub. Copy it to each machine by hand.

## 5a. Add SIAM guidance (recommended)

The SIAM guidance is a free download from scopism.com, so you can get it straight onto the work machine:

1. Download the SIAM Body of Knowledge (and the Process Guides if listed) from scopism.com.
2. Save as `.md` or `.txt` in `kb-siam/` if Kiro won't index the PDF.
3. Restart Kiro.

`kb-siam/` is never pushed to GitHub.

## 6. Change how the agents review

Make changes on the Mac, then push and pull.

| To change | ITIL reviewer | SIAM reviewer |
|---|---|---|
| What gets checked | `rubric/itil5-product-rubric.yaml` | `rubric/siam-rubric.yaml` |
| How the review is done | `.kiro/prompts/itil5-reviewer.md` | `.kiro/prompts/siam-reviewer.md` |
| What applies to each document type | `.kiro/skills/itil-doc-classification/SKILL.md` | `.kiro/skills/siam-doc-classification/SKILL.md` |
| How each area is judged | `.kiro/skills/itil-cross-cutting/SKILL.md` | `.kiro/skills/siam-checks/SKILL.md` |
| Report layout and scoring (shared) | `.kiro/skills/report-format/SKILL.md` | same file |
| Local terms and house rules (shared) | `.kiro/steering/org-context.md` | same file |

Then:

```bash
git add .
git commit -m "What you changed"
git push
```

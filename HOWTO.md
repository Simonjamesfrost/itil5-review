# How to set up and use the ITIL 5 review agent

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

If the agent isn't found or Kiro complains about the config, run `/upgrade-agent diagnostics` inside Kiro – it will name the field it doesn't like.

## 3. Review a real document

1. Save the document as Markdown (`.md`) or plain text (`.txt`).
   - Word: File → Save As → Plain Text.
   - Confluence: copy the page into a new `.md` file.
   - PDF: copy the text into a `.md` file.
2. Put it in `inbox/`.
3. In Kiro: `review inbox/<file name>`
4. Open the report in `reviews/`.

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

## 6. Change how the agent reviews

Make changes on the Mac, then push and pull.

| To change | Edit |
|---|---|
| What gets checked | `rubric/itil5-product-rubric.yaml` |
| How the review is done | `.kiro/prompts/itil5-reviewer.md` |
| Report layout and scoring | `.kiro/skills/report-format/SKILL.md` |
| Which activities apply to each document type | `.kiro/skills/doc-classification/SKILL.md` |
| Local terms and house rules | `.kiro/steering/org-context.md` |

Then:

```bash
git add .
git commit -m "What you changed"
git push
```

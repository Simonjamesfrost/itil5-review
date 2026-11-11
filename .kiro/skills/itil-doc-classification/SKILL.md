---
name: itil-doc-classification
description: ITIL reviews only. Work out what type of document is being reviewed and which ITIL Product and Service Lifecycle activities it should cover. Use at the start of every review.
---

# Document classification

Decide the document type from its title, purpose statement and content – not just the file name. Then pick the lifecycle activities in scope.

## Lifecycle activities

| Activity | In short |
|---|---|
| discover | understanding needs, opportunities, market and value |
| design | shaping the product or service, its experience and architecture |
| acquire | getting the resources, suppliers and components needed |
| build | creating, integrating and testing components |
| transition | moving changes into live use safely |
| operate | running the technology and keeping it healthy |
| deliver | providing the service to consumers day to day |
| support | helping users and fixing issues |

## Default mapping

Use this as a starting point. Adjust if the document clearly covers more or less.

| Document type | Primary activities | Secondary (check lightly) |
|---|---|---|
| Product brief / business case | discover, design | acquire |
| Product roadmap | discover, design, build | transition |
| Service design package | design | acquire, build, transition, operate, deliver, support |
| Supplier / acquisition proposal | acquire | design, transition |
| Build or test plan | build | design, transition |
| Release / deployment / transition plan | transition | build, operate, support |
| Runbook / operations guide | operate | support, transition |
| Support model / service desk process | support | deliver, operate |
| Service level document / service review | deliver | support, operate |
| Improvement proposal | the activity being improved | discover |

Primary activities: score every criterion. Secondary: score only criteria where the document should reasonably say something; mark the rest N/A.

Cross-cutting criteria always apply, scaled to the document's size.

## Output

Start the report with:

- **Document type:** …
- **Primary activities:** …
- **Secondary activities:** …
- **Confidence:** High / Medium / Low, with one line of reasoning if not High.

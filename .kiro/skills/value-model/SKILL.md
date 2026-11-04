---
name: value-model
description: What a value creation model contains and how to extract it from documents. Use at the start of every value-modelling task and when writing the model document.
---

# Value creation model

A value creation model explains how a service helps its consumers get an outcome they care about, who does what to make that happen, and how you would know it worked.

## Parts of the model

| # | Part | Question it answers | Look for in the source |
|---|---|---|---|
| 1 | Value proposition | What does this service offer, to whom, and why would they want it? | purpose, scope, service catalogue, "why" sections |
| 2 | Consumers and outcomes | Who uses it, and what outcome do they get? | named groups, roles, personas, user needs, problems solved |
| 3 | Value co-creation | What does the provider do, what does the consumer do, and what do they do together? | request routes, onboarding, training, feedback, champions, sign-offs |
| 4 | Value stream | What are the steps from demand to value, and who owns each? | process flows, tiers, intake paths, lifecycle stages |
| 5 | Architecture and integrations | What systems, suppliers and teams make it work, and how do they connect? | system lists, interfaces, APIs, contracts, hand-offs |
| 6 | Four dimensions | Are people, technology, suppliers and processes all covered? | roles, tools, vendors, procedures |
| 7 | Consumer journey | What is it like to use the service, step by step? | request, access, support, change, exit |
| 8 | Value measures | How would we know value is being created? | targets, SLAs, adoption, satisfaction, cost, time saved |

## Mapping to lifecycle activities

Use these eight activities as the backbone of the value stream (from the rubric). Place each step of the source process under the activity it best fits.

| Activity | Typical steps |
|---|---|
| discover | understand consumer needs, opportunity, demand |
| design | shape the offering, experience, architecture |
| acquire | get licences, suppliers, components |
| build | create, configure, integrate, test |
| transition | move a change into live use safely |
| operate | run the technology, keep it healthy |
| deliver | provide the service to consumers day to day |
| support | help users, fix incidents and problems |

An activity with no steps in the source is a **Gap** in the stream. Say so on the diagram.

## ITIL 4 concepts to use (label as unverified for Version 5)

- **Service relationship** – provider and consumer work together through provision, consumption and relationship management. Use it for part 3.
- **Four dimensions** – organisations and people; information and technology; partners and suppliers; value streams and processes. Use it for part 6.
- **Guiding principles and governance** – use only as a light annotation, for example where governance approvals sit in the stream.

## Extracting from documents

1. List every named consumer group, system, supplier, role, team, process and document reference.
2. For each, note the source section.
3. For each consumer group, write the outcome they get in their own terms. If the source does not state one, draft one and mark it **Unconfirmed**.
4. For each step of the stream, note owner, system and input/output.
5. Record any statement of status ("built", "not yet built", "proposed", "blocked", "no ETA") and carry it into the diagrams.
6. Where two sections disagree, show both in the open questions rather than choosing one.

## Status labels

| Status | Meaning | Use when the source says… |
|---|---|---|
| Built | Works today | "built", "validated", "works today", "established" |
| Proposed | Designed or agreed, not yet live | "proposed", "target state", "planned" |
| Gap | Needed but absent | "not built", "no ETA", "gap", "no CI", "none" |
| Unconfirmed | Inferred by the modeller | nothing explicit |

## Completeness checklist

Before saving, check:

- [ ] Value proposition fits in two sentences
- [ ] Every consumer group has at least one outcome
- [ ] Every outcome has at least one measure, or is flagged as having none
- [ ] Every lifecycle activity appears in the stream, even if only as a Gap
- [ ] Every system and supplier named in the source appears in the architecture diagram
- [ ] Each diagram has a caption
- [ ] Assumptions, gaps and open questions are listed once at the end

## Model document template

```markdown
# Value Model: <service name>

**Created:** <YYYY-MM-DD> · **Source:** <file paths> · **Status:** Draft for confirmation

## 1. Value proposition
<Two sentences. Then the diagram.>

## 2. Consumers and outcomes
<Table: consumer group | outcome | evidence | status. Then the diagram.>

## 3. Value co-creation
<Provider does / consumer does / done together. Then the diagram.>

## 4. Value stream
<Table: activity | steps | owner | system | status. Then the diagram.>

## 5. Architecture and integrations
<Diagram. Then a table of integrations with status.>

## 6. Four dimensions
<Diagram. Then one line on any thin dimension.>

## 7. Consumer journey
<Diagram. Then the pain points seen.>

## 8. Value measures
<Table: outcome | measure | target | baseline | source | status.>

## Assumptions, gaps and open questions
<Three short lists.>

## Notes
- Knowledge base used: Yes/No
- ITIL 4 concepts used (not yet checked against Version 5): <list>
- Limitations: <e.g. diagrams not rendered, sources not read>
```

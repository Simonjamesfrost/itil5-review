---
name: siam-doc-classification
description: SIAM reviews only. Work out the document type, SIAM roadmap stage, whose perspective it is written from, the SIAM structure, and which SIAM rubric areas are in scope. Use at the start of every SIAM review.
---

# SIAM document classification

Decide from the document's purpose and content, not its file name.

## 1. Is SIAM relevant?

SIAM applies when two or more service providers (internal teams count) must work together to deliver a service, usually with someone acting as service integrator. If the document involves one provider only and no handoffs between parties, SIAM adds little. Say so and stop.

## 2. Perspective – who wrote it, for whom

| Perspective | What to expect |
|---|---|
| **Customer** (incl. retained capabilities) | Strategy, sourcing, business case, contracts, governance at strategic level. Owns accountability. |
| **Service integrator** | End-to-end process models, policies, data standards, governance boards, end-to-end reporting, onboarding. |
| **Service provider** | How its own processes and services plug into the integrator's process models, data standards and forums. |

If unclear, say so and assume the customer view.

## 3. SIAM structure (if stated)

Externally sourced integrator · Internally sourced integrator · Hybrid integrator · Lead supplier as integrator · Not stated.

Lead supplier and internal integrator structures raise impartiality and segregation-of-duties questions (see `siam-checks`).

## 4. Roadmap stage

| Stage | Typical documents |
|---|---|
| Discovery & Strategy | SIAM strategy, outline business case, current-state map, sourcing strategy, governance principles |
| Plan & Build | Detailed SIAM model, process models, governance terms of reference, RACI, contract schedules, performance and reporting framework, tooling strategy, onboarding plan |
| Implement | Transition plan, onboarding plan, handover plan, knowledge transfer plan, communications plan |
| Run & Improve | Board packs, service reviews, end-to-end reports, improvement register, audit reports, cross-provider procedures |

## 5. Areas in scope – default mapping

Rubric areas: STR strategy and business case · LAY layers and roles · SVC service model · GOV governance · PRC process integration · DAT data and tooling · CON contracts · PER performance and reporting · COL collaboration · TRN onboarding, transition and exit · IMP improvement.

| Document type | Primary areas | Secondary (check lightly) |
|---|---|---|
| SIAM strategy / business case | STR, LAY, SVC | GOV, CON |
| SIAM model design | LAY, SVC, GOV, PRC | DAT, PER, COL, IMP |
| Governance framework / board terms of reference | GOV, LAY | PER, IMP, COL |
| Cross-provider process model or procedure (incident, change, problem, request) | PRC, LAY | DAT, PER, COL |
| Contract, schedule, SOW, collaboration agreement | CON, LAY | PER, DAT, TRN |
| Supplier proposal / bid | CON, TRN, PRC | LAY, PER |
| Performance and reporting framework, service review pack | PER | GOV, IMP |
| Tooling strategy / integration design | DAT | PRC, CON |
| Onboarding, transition, exit or handover plan | TRN | LAY, DAT, CON |
| Improvement plan / register | IMP | PER, COL |

Primary areas: score every criterion. Secondary: score only criteria the document should reasonably cover; mark the rest N/A. Criteria whose `applies_to` field excludes the author's perspective are N/A.

## Output

Start the report with:

- **Document type:** …
- **Perspective:** Customer / Service integrator / Service provider
- **SIAM structure:** …
- **Roadmap stage:** …
- **Primary areas:** …
- **Secondary areas:** …
- **Parties named:** list the organisations and teams the document mentions
- **Confidence:** High / Medium / Low, with one line of reasoning if not High

---
name: siam-checks
description: SIAM reviews only. How to judge each SIAM rubric area, how to adjust for the author's perspective, and the common multi-provider failure patterns to look for. Use when scoring criteria in rubric/siam-rubric.yaml.
---

# SIAM checks

## The core test

For every process, decision, measure and obligation in the document, ask:

1. **Who is accountable** – one named party?
2. **Who does the work** – which provider, and where does it hand over to the next?
3. **What standard applies** – a shared definition, policy or data standard, or each party's own?
4. **How would anyone know it is working** – end to end, not just per provider?

Most SIAM gaps are a blank answer to one of these for one of the parties.

## Adjusting for perspective

- **Customer documents:** expect accountability, strategy, sourcing, contracts, strategic governance. Do not expect detailed process models; do expect the document to say who will design them.
- **Integrator documents:** expect end-to-end process models, policies, data standards, structural elements, end-to-end reporting, onboarding. This is where most criteria apply.
- **Provider documents:** expect alignment – how the provider's process connects to the integrator's process model, uses the shared data standards, takes part in forums, and reports in the common format. Do not mark down for missing ecosystem-wide design.

## How to judge each area

**STR – strategy and business case.** Clear objectives and value, a reason SIAM fits, tailored to the organisation's size and maturity, benefits tracked against the case.

**LAY – layers and roles.** All three layers visible. Integrator treated as a separate logical role even when internal. Retained capabilities defined. A RACI that covers every party. Integrator's authority to act for the customer stated, with limits.

**SVC – service model.** Every service element has exactly one accountable provider and nothing is left unassigned (mutually exclusive, collectively exhaustive). Dependencies between providers mapped.

**GOV – governance.** Strategic, tactical and operational levels. Boards, process forums and working groups with purpose, members, cadence and decision rights. Control owners named. Risk includes the build-up of small risks across parties. Dispute route and audit rights.

**PRC – process integration.** One end-to-end owner per process. Process model shows purpose, activities, inputs and outputs between parties, controls, measures and supporting policies. Shared definitions (priority, severity, change types). Handoffs and coordination across providers explicit.

**DAT – data and tooling.** Who owns the data and keeps access if a provider leaves. Shared data dictionary. Tooling strategy and ownership. Integration between toolsets. What configuration data is shared and who maintains it. Ownership of knowledge articles and other artefacts.

**CON – contracts.** Integration obligations written in (process models, tooling, data, forums, collaboration). Integrator recognised as the customer's agent. Common services schedule. Clear line between a performance breach and a contract breach. Remedies apportioned fairly when several providers contributed. Exit schedule. Room to change.

**PER – performance and reporting.** End-to-end measures as users experience them, plus each provider against its targets, plus the integrator's own performance. Delivery of obligations measured separately from performance. Common calculation rules and reporting periods. Provider reports checked. Measures that cannot drive bad behaviour.

**COL – collaboration.** Collaboration designed in, not hoped for: forums, a collaboration agreement, behaviour measures, a way to handle commercial confidentiality, conflict resolution, knowledge sharing between providers.

**TRN – onboarding, transition and exit.** Written onboarding plan with acceptance criteria per process and milestones. One integrated plan across providers with gaps and overlaps checked. Knowledge transfer from the outgoing provider, including keeping key staff. In-flight work baselined at handover. Current service protected during the move. Planned offboarding.

**IMP – improvement.** Shared improvement register, on governance board agendas, all providers involved, lessons shared, a way to prioritise end-to-end improvements over local ones.

## Failure patterns to look for

Raise these as findings against the criterion shown.

| Pattern | What it looks like | Criterion |
|---|---|---|
| Integrator does everything | Document assumes the integrator runs all process activity, not just integration | LAY-04, PRC-01 |
| Copied model | A large-organisation SIAM model applied without tailoring | STR-03 |
| Incident ping-pong | Each provider has its own resolution target, nothing protects the end-to-end target, so tickets get passed on | PRC-05, PER-06 |
| Every provider green, customer red | Reports show all providers meeting SLAs but no end-to-end measure | PER-01 |
| Missing column | RACI or escalation path with no integrator or no customer | LAY-03 |
| Orphan or shared service element | A component with no provider, or two providers both "responsible" | SVC-01 |
| Favoured provider | Lead supplier or internal team managed more lightly than others | LAY-06 |
| Locked-in data | Integrator's or provider's tool holds the records with no customer access on exit | DAT-01 |
| Zombie contract | Exit leaves obligations hanging, or no exit schedule at all | CON-07 |
| Sink-or-swim onboarding | New provider expected to "pick it up" with no plan or acceptance criteria | TRN-01 |
| Bad-behaviour metric | A measure that rewards passing work on, closing early or gaming the clock | PER-06 |
| Confidentiality standoff | Providers asked to share processes or data with no rules for commercially sensitive material | COL-03 |

## Priority

- **High** – could cause service failure across providers, unmanaged accountability, contract dispute, lock-in, or non-compliance
- **Medium** – weakens integration but would not stop the service working
- **Low** – clarity, wording, nice to have

In a regulated setting, gaps in audit rights, control ownership, change approval across parties and data integrity are High.

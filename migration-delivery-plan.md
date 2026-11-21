# How I would lead the first migration wave

This is a proposed delivery plan for a new engagement. The client owns the change approval and business acceptance. I would make the engineering team accountable for a reviewable design, reproducible evidence and a handover that operations can use.

| Stage | My engineering deliverable | Exit decision |
| --- | --- | --- |
| Discover | Versioned source and target inventories, external initiator list, business deadlines, and named owners for calendars, credentials and downstream applications. | Can we account for what starts the work and what counts as business completion? |
| Select a pilot | One representative of each high-risk pattern, a business owner, an observation window and a reversible cutover scope. | Does the pilot exercise the difficult controls as well as common wrappers? |
| Build and review | Target calls, their effective parameters, execution route, identity, dependency, retry and error handling. Log intentional differences with approvals. | Can an independent reviewer reconstruct why each important difference exists? |
| Rehearse | Aligned inputs, expected negative cases, externally visible receipts and observed outputs. Where side effects exist, agree isolation or another safe test method with the application owner. | Which workflows can go, which must hold, and who owns the remaining evidence? |
| Transfer ownership | Last eligible source occurrence, first intended target occurrence, treatment of queued work and proof that only the intended scheduler initiates the wave. | Can the change owner identify the exact handoff and stop the release if ownership is ambiguous? |
| Stabilise and hand over | First-live reconciliation, exception register, escalation contacts, recovery branches and support walkthrough. | Can support resolve a realistic failure using the handover and the same execution references? |

## How I would size the work

Group definitions by execution pattern, then sample representative calls. Fifty wrappers can be cheap to build and expensive to validate if their argument overrides, calendars or side effects differ. I would report distinct patterns, exceptions per pattern, external dependencies, unowned controls and evidence still missing. After the pilot, observed build and validation effort can support a wave estimate.

| Measure I would show the sponsor | What it answers |
| --- | --- |
| Mapped source calls / in-scope calls | Inventory coverage. Record the excluded or deliberately consolidated calls. |
| Critical behaviours passed / critical behaviours agreed | Whether the pilot actually exercised the release criteria. Keep unknowns visible. |
| Business outputs reconciled / outputs expected | Whether the intended business result arrived with the correct identity and content. |
| Unresolved external side effects | Whether a timeout, partial delivery or posting blocks a replay or transfer. |
| Waves ready, held, or awaiting an owner | Which decisions the sponsor can make now. |

**Pilot challenge I welcome in an interview.** Give me an anonymised source chain, its target design and one disputed run. I will trace when it became eligible, where it ran, what external effect it produced, and what additional evidence I would require before recommending release.

[Open the completed example handover](cutover-handover.md) · [Inspect the 12-row rehearsal ledger](rehearsal-evidence.csv)

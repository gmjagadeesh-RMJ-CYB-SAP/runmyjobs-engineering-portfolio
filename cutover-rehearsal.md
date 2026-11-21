# Would you release this migration wave?

A cutover chair gives you five minutes. Three independent business workloads have moved into RMJ. Inventory reports 12 of 12 definitions mapped. Read the evidence, make each call, then expand my answer. The jobs, observations, totals and decisions in this exercise are fictional.

[Download the three-wave, choose-your-path PDF](migration-decision-room.pdf). Open it in a PDF reader to follow the decision buttons, or use the expandable answers below.

**Your authority in this exercise.** You can recommend which wave to release. The finance owner authorises posting recovery, the application owner checks remote receipts, and operations controls the active scheduler. A release decision applies to one wave at a time.

### 1 · The steering meeting

Wave A creates a read-only reconciliation. Wave B consumes an inbound delivery. Wave C submits a ledger posting. All have four source jobs and four target jobs. A manager wants one green tick for the migration.

**Choose a decision.** Approve all twelve, hold all twelve, or split the release decision?

<details>
<summary>Reveal my decision and the evidence I need</summary>

**Split the decision by independent wave.** The inventory establishes coverage. To decide whether to transfer ownership I need the business date, execution eligibility, external side effects and recovery evidence for each wave. In this rehearsal no wave triggers either of the other two. If a shared event or scheduler switch coupled them, I would revisit that assumption before releasing A.

</details>

### 2 · The calendar and the control total

A01 was tested on six dates including a closure and a month boundary. A03 waited for the correct parent’s snapshot. A04 produced 120 keyed records and a total of 8,420.00 on both paths. The keyed digest also matched. Rehearsal outputs were isolated. The source owner has agreed the handoff window.

**Choose a decision.** Release Wave A immediately, release at the ownership handoff, or hold it for last month’s volume?

<details>
<summary>Reveal my decision and first-live check</summary>

**Recommend A for the controlled handoff.** Matching row counts and totals alone can hide records posted against the wrong key. Here the same input snapshot and keyed digest also agree. Before activation, operations records the source’s last eligible run, confirms that source initiation is paused for this scope and identifies the target’s next intended business date. The report owner compares the first live target output with the rehearsal controls.

I would hold A if the source and target could both publish for that first live period, even with all four rehearsal controls passing.

</details>

### 3 · A green parser and an old file

At window opening yesterday’s file is still present. The source watcher waits. The target releases B02 immediately. The parser completes, and a duplicate-delivery test for the staging step passes.

**Choose a decision.** Accept the successful parser, remove the stale file manually, or hold the inbound wave?

<details>
<summary>Reveal my decision and the counterexample that closes it</summary>

**Hold B.** The business rule is *new delivery for this window*. The target currently accepts *file exists*. A green parser shows it can parse the wrong input. Removing yesterday’s file would erase the test condition and leave the difference in place.

I would ask the integration owner to rehearse four inputs: no file, yesterday’s file, one fresh valid file, and the same fresh delivery again. The first two must produce zero releases. The new delivery must release once and the replay must leave the staged batch count at one. Capture the producer reference, file key and batch receipt together.

</details>

### 4 · A timeout after the remote system accepted the request

C02 submits key **W24-L1**. The scheduler times out. The receiving application shows one acceptance receipt. Final ledger confirmation is pending, and C04 has correctly held the completion notification. The source schedule could be restored quickly.

**Choose a decision.** Retry the target, re-enable the source immediately, or reconcile first?

<details>
<summary>Reveal my decision and recovery branches</summary>

**Hold C and reconcile before replay.** The finance owner checks the ledger by business key and the application owner traces the receipt. If it posted once with the correct amount, resume from downstream verification using the original reference. If acceptance is still pending, keep ownership with the investigation and recheck. If the application proves rejection, the ledger shows no posting and replay is authorised, permit one controlled resubmission with the agreed key and record its result. Escalate a duplicate, conflicting evidence or an unknown outcome to the finance owner.

Restoring the source scheduler changes who initiates future work. It does not reverse a posting that already happened. The receiving application decides what its acceptance receipt means.

</details>

## Chair’s handoff

| Wave | Recommendation | Evidence that changes the call |
| --- | --- | --- |
| A · Read-only reconciliation | Ready at the agreed handoff | Both schedulers could still publish for the same period, or first-live output differs. |
| B · Inbound delivery | Hold | The corrected freshness and replay tests pass with the same producer, file and staging keys. |
| C · Financial posting | Hold and reconcile | Finance confirms the final ledger state and the application owner reconciles it to the original receipt. |

[Download the evidence ledger](rehearsal-evidence.csv) · [Open the filled shift handover](cutover-handover.md) · [Return to the portfolio](README.md)

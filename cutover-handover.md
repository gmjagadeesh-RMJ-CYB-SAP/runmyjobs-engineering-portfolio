# Cutover handover · rehearsal shift

**Decision at handoff.** Release A at the agreed ownership transfer. B stays with the source scheduler while its watcher is corrected. C stays on hold while finance reconciles a remote acceptance. All observations below belong to the [fictional migration rehearsal](cutover-rehearsal.md).

| Wave | Who owns the next action | State to preserve | Next shift closes the item when… |
| --- | --- | --- | --- |
| A · Reconciliation | Operations lead and report owner | Last eligible source run, first intended target date, immutable input snapshot and baseline digest | One scheduler initiated the first live run and the recipient confirms one correct report. |
| B · Inbound | Integration owner | Old file in the test window, original event observation, file key and target batch receipt | Absence and stale-file tests release nothing. A fresh file loads once. Its replay creates no new batch. |
| C · Posting | Finance and application owners | W24-L1, original receipt, target timeout and held completion notification | The ledger owner confirms zero, one or multiple postings and records which recovery branch was authorised. |

## What I ask before the switch

1. **Draw the ownership boundary.** List native schedules, external API callers, event producers and manual submission routes for this wave. Record who controls each route. Pausing one submit frame does not establish that other initiators are quiet.
2. **Identify the last and next occurrence.** Record the source’s last eligible business period, the target’s first intended period, the time zone and any already-queued work. An interval straddling cutover deserves an explicit owner.
3. **Agree the business comparison.** For A, compare the immutable input ID, output key set, count, amount and keyed digest. For B, follow one delivered file into one staged batch. For C, reconcile the posting key and receiving-system record.
4. **Name the decision makers.** Operations controls initiation. The application owner interprets a remote acknowledgement. The business owner accepts the output or authorises recovery after a side effect. Record open risks in the handover.

## If the first live output differs

| Situation | Immediate evidence to keep | Recovery decision |
| --- | --- | --- |
| Target produced a read-only report with different content | Source and target business dates, snapshots, keyed differences and recipient status | Hold distribution. Regenerate against the agreed snapshot only after the owner identifies the difference. |
| Target already moved a source file | File identity, staged copy and consumer receipt | Establish who consumed it before restoring the source route. Avoid a second delivery of the same input. |
| Target timed out after submitting externally | Local execution, remote receipt, business key and current remote state | Ask the receiving owner to reconcile first. Resume from the earliest step that still needs to happen. |
| Scheduler ownership is unclear | Both schedulers’ queued and active occurrences plus external caller evidence | Hold new initiation for the affected scope under the approved change and assign one owner before resuming. |

**Shift note, Wave C.** “One remote acceptance exists for W24-L1. The ledger result is outstanding. Completion notification remains held. Finance owns the reconciliation. The next shift is to check the original key before considering another submission.”

[Evidence ledger](rehearsal-evidence.csv) · [Migration field guide](migration-field-guide.md)

# Migration field guide · 18 behaviour checks

I use a behaviour check when a source and a target can look alike in an inventory but make different decisions at runtime. These are original, fictional test scenarios for an interview or migration design review. The applicable scheduler version and the customer’s business rules determine the expected result.

## AutoSys to RunMyJobs

| # | Control | Counterexample I would test | Acceptance evidence |
| --- | --- | --- | --- |
| 01 | File watcher | Leave yesterday’s matching file in place when today’s window opens. Deliver a new file later and repeat its delivery. | Identify the correct file and release exactly the intended occurrence. Record both file identity and consuming run. |
| 02 | Box and predecessor | A prior box completed successfully while the current box still has a blocked child. | The successor waits for the agreed predecessor occurrence. Trace source box, target parent and child IDs together. |
| 03 | Calendar exception | A month-end holiday moves the last working day into the prior week. | Compare evaluated dates in the business time zone and retain the exception-calendar version. |
| 04 | Runtime and retries | A task fails after a remote service accepted its request. | Record original attempt, external receipt and retry decision. Confirm the business operation occurs the intended number of times. |
| 05 | Machine and queue mapping | A queue routes to a different eligible host with a different service identity. | Show where the occurrence actually ran and whether that identity could read the intended input. Record approved routing differences. |
| 06 | Global variables and snapshots | A global changes after inventory export but before the rehearsal. | Freeze or record the value and business period used on each side. A mismatch in snapshots sends the finding back for aligned evidence. |

## UC4 / Automic to RunMyJobs

| # | Control | Counterexample I would test | Acceptance evidence |
| --- | --- | --- | --- |
| 07 | JOBP predecessor paths | Two tasks share a successor. Only one has finished. | The target follows the agreed dependency logic for each predecessor outcome. Record the branch, not just task order on screen. |
| 08 | Repeated calls and arguments | The same wrapper is called twice with a different file date and an empty optional argument. | Compare the effective arguments for both calls, including the empty position. Confirm the actual input file for each. |
| 09 | VARA reads and writes | Two business periods update the same lookup while the earlier period is still running. | Trace key, scope, value and timing. Each consumer must read the value belonging to its occurrence. |
| 10 | Event or time trigger | A condition stays true through consecutive checks and crosses midnight. | Compare how many occurrences are released and which business date owns each. Document reset and consumption rules. |
| 11 | Return-code semantics | A warning should allow a dependent step to continue; another return code should route to recovery. | Exercise both outcomes and record status plus successor branch. A matching overall “Completed” can hide a skipped branch. |
| 12 | Failure notification | Two sibling jobs fail under one parent and a parent summary also qualifies. | Trace each failure to the correct business impact. Show which messages or tickets were generated and which execution each references. |

## IBM TWS / IWS to RunMyJobs

| # | Control | Counterexample I would test | Acceptance evidence |
| --- | --- | --- | --- |
| 13 | Job-stream occurrence and business date | A stream starts before midnight and the consuming job becomes eligible after midnight. | Agree the logical business date and verify that the target selects the intended predecessor occurrence. |
| 14 | Run cycles and exclusions | A normal weekday matches an exclusion and a special inclusion in the same period. | Compare the resolved occurrence list under the agreed calendar precedence. Include the boundary dates in both exports. |
| 15 | Cross-stream dependencies | A stream with several daily occurrences follows another stream that also runs several times. | Pair each consuming occurrence with the required producer. Demonstrate which earlier successful run is eligible to satisfy the dependency. |
| 16 | Workstation or pool routing | The preferred worker is unavailable while an alternate worker can still run. | Verify the route, service identity and application reachability of the worker that receives the job. |
| 17 | Resources and concurrency | Two eligible occurrences contend for a capacity-one resource. | Capture one active holder and one waiting occurrence. Confirm release after completion and after an abnormal end. |
| 18 | Rerun and carry-forward policy | A previous business period remains unfinished when the next period is generated. | Agree whether to retain, skip or independently schedule the next occurrence. Verify the resulting periods, dependencies and side effects. |

## What a defensible finding contains

**Source intent → aligned source and target versions → effective control → observed execution or missing evidence → business impact → owner and next check.** A mirrored process name is a useful inventory key. It is a poor substitute for observed behaviour.

[Implemented AutoSys audit](autosys-migration.md) · [Cutover decision exercise](cutover-rehearsal.md) · [Delivery plan](migration-delivery-plan.md)

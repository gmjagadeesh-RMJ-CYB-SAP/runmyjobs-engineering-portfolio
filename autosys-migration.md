# Reviewing an AutoSys to RunMyJobs migration

A comparison can identify two different definitions. The engineering question is whether the difference changes when a job starts, how it runs, or what happens after failure. I built a review workflow for this question during an AutoSys migration in June and July 2026.

## How the review worked

| Input | What I built or collected | What it lets the reviewer check |
| --- | --- | --- |
| AutoSys | A Python parser for Job Information Language (JIL), with calendar, machine, global and resource inputs | The source condition, its operands and any supporting definitions needed to interpret it. |
| RunMyJobs | Java / RedwoodScript extraction of target configuration and execution controls | Where a control sits on the target, including the surrounding workflow context. |
| Comparison | CSV and ZIP evidence plus review workbooks | The source and target versions used, the observed difference and the next action. |

I treated file-watcher and promotion diagnostics as part of the migration review. A newer source export paired with an older target can produce a plausible but misleading finding. I kept the input versions with each comparison and revised the rules as feedback and execution results came in.

## A worked finding

Suppose a source job waits for an inbound file. In the target export, its mapped job has no file condition. That is enough to open a review item. Before calling it a defect, I would trace the enclosing chain, identify the event the chain consumes, and locate its producer. A similarly named event is weak evidence. The producer must represent the same file condition and release the intended run.

The [sample review sheet](migration-review.csv) follows this example and three others. All four rows are fictional. Each row ties a claim to a source version, target version and a check that could change the decision.

| Disposition | When I would use it |
| --- | --- |
| Equivalent for the tested case | The direct or inherited control accounts for the source behaviour in the stated scenario. Record any untested boundary. |
| Defect | The inputs refer to the same scope and the evidence shows a consequential behavioural difference. |
| Needs context | A parent chain, event producer, calendar or other input is missing. Name the missing item. |
| Inputs misaligned | The versions cover different change sets. Repeat the comparison against an aligned pair. |

The implemented workflow produced traceable findings. Any count of defects or matched jobs needs the specific population, input versions and review decisions behind it.

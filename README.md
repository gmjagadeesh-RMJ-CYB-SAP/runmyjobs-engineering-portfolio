# RunMyJobs engineering portfolio

I'm Jagadeesh Gadimuthaka (Jaga), a Redwood RunMyJobs consultant based in Cambridge, UK. I build workflows across SAP and enterprise applications, review scheduler migrations, and give operators a way to trace a result back to the run that produced it.

For a migration engineering role, start with the [AutoSys audit](autosys-migration.md) and its [worked review sheet](migration-review.csv). For an integration role, start with [cross-system orchestration](cross-system-orchestration.md). For a short introduction to the work, [download the portfolio brief](Jagadeesh_RunMyJobs_Portfolio_Brief.pdf).

## Selected engineering work

| Case | My contribution | What I could verify |
| --- | --- | --- |
| [AutoSys to RunMyJobs](autosys-migration.md) | Built a source parser, RMJ extractor and comparison reports | Reviewers could trace a difference to source and target evidence, then record the next check. |
| [Cross-system orchestration](cross-system-orchestration.md) | Connected SAP and non-SAP steps through RMJ | Salesforce and webMethods trigger tests returned HTTP 200 and application success messages. |
| [Azure DevOps releases](azure-devops-releases.md) | Worked on object export to Azure Repos and CAR upload from Azure Pipelines | The binary upload worked. Target import received limited validation. |
| [Nested-workflow monitoring](nested-workflow-monitoring.md) | Enhanced an existing monitor to follow a selected child or subchain | Testing confirmed direct monitoring of a nested workflow. |
| [Report delivery to SharePoint](report-delivery.md) | Routed RMJ report attachments through email and Power Automate | Testing confirmed email delivery and the first flow. The second route still needs destination evidence. |
| [Email and ServiceNow routing](notification-routing.md) | Added table-driven routing around Redwood's ServiceNow connector | Tests produced email and incidents. Restart and throttling behaviour depend on the implementation version. |

A separate [SAP Datasphere diagnostic note](datasphere-connectivity.md) shows how I narrowed a connector problem after DNS, TCP and TLS checks passed.

The cases use anonymised project descriptions. The worked review sheet uses fictional job names, export versions and observations. This repository contains documentation and sample evidence only.

[Jagadeesh Gadimuthaka on LinkedIn](https://www.linkedin.com/in/jagadeeshrmj/)

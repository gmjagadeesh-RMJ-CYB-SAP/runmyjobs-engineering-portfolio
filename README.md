# Jagadeesh Gadimuthaka | Redwood RunMyJobs engineering

I'm a RunMyJobs consultant based in Cambridge, UK. I build cross-system workflows, develop migration review tools and give operators a way to trace a business process to the execution that needs attention.

## Featured demo · Which child run should support open?

I enhanced a custom RMJ monitor to follow selected subchains and open the corresponding native Process view. This short visual replay uses fictional job IDs to illustrate one monitoring decision. Two parent runs start the same child workflow. A completion from the older run arrives after the newer child has started.

![Animated replay of six fictional observations. Child 810 remains selected after older child 850 finishes and a stale Running update arrives.](workflow-monitor-replay.gif)

At **08:07 UTC**, the operator should see **parent 71, child 810, Waiting for input**. At **08:12**, the same child shows **Completed**. Selecting the largest Job ID would take the operator to 850. Using the last message alone would briefly show the wrong status for 810.

[Read the monitor case study](nested-workflow-monitoring.md) · [Download the two-page portfolio brief](Jagadeesh_RunMyJobs_Portfolio_Brief.pdf)

**Source access.** This repository contains the visual demo and case studies. I keep implementation code private. If you would like a walkthrough or permission to review a specific sample of my own code, [contact me on LinkedIn](https://www.linkedin.com/in/jagadeeshrmj/). Any source review requires my explicit approval.

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

The cases use anonymised project descriptions. The worked review sheet uses fictional job names, export versions and observations.

[Jagadeesh Gadimuthaka on LinkedIn](https://www.linkedin.com/in/jagadeeshrmj/)

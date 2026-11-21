# Engineering work by discipline

My RunMyJobs work spans the chain that runs the business process, the interfaces it calls and the tools needed to operate it after handover. The first table points to project cases. The second shows how I investigate additional scenarios across the same estate.

## Project work I can walk through

| Discipline | Contribution | Engineering judgement |
| --- | --- | --- |
| Source extraction | Parsed AutoSys JIL with machine, global, calendar and resource context for migration review. | A JIL file can reference a control whose definition lives in a separate export. I record missing input before classifying a difference. |
| Target extraction | Collected RMJ configuration and execution controls using Java/RedwoodScript. | A value can be inherited or supplied on a chain call. The leaf definition alone can misrepresent the effective behaviour. |
| Migration evidence | Combined the source and target in CSV evidence and review workbooks. | A reviewer needs the source intent, target evidence and next test for each finding. [AutoSys audit](autosys-migration.md) |
| Cross-system build | Worked on SAP and non-SAP orchestration across ECC, BODS, Salesforce, webMethods, Datasphere, BTP CPI and CIDS. | Trigger acknowledgement and the downstream business result have different owners. [Integration case](cross-system-orchestration.md) |
| Release automation | Worked on object and related-object export, repository/branch selection, pipeline upload and ruleset handling. | Record the exact archive uploaded and validate import separately. [Azure DevOps case](azure-devops-releases.md) |
| Monitoring development | Enhanced an existing monitor to follow selected nested workflows and navigate to the matching execution. | A reused child definition can occur under two parents. Use the execution reference the operator actually saw. [Monitor case](nested-workflow-monitoring.md) |
| Incident routing | Implemented table-driven recipients, incident metadata and separate channel switches around the ServiceNow connector. | A child failure and a parent summary can refer to the same incident. Define the owner of the notification. [Routing case](notification-routing.md) |
| Output distribution | Prepared generated RMJ report attachments and routed them through an inbox and Power Automate to SharePoint. | Inbox receipt is an intermediate checkpoint. Destination contents close the delivery. [Report case](report-delivery.md) |
| Connectivity diagnosis | Checked DNS, TCP and TLS reachability for the tested Datasphere and authentication endpoints. | A successful handshake narrowed the next investigation to OAuth and the actual business request. [Diagnostic note](datasphere-connectivity.md) |

## How I investigate work outside the scheduler

These are practical interview scenarios. Each pairs an initial symptom with the next evidence I would request.

| Area | Symptom | Evidence and decision |
| --- | --- | --- |
| SAP ECC ABAP | The program ran but selected the wrong population. | Match the SAP job occurrence to the RMJ run. Compare program, variant and effective call values. Identify which call supplied the variant before changing a reusable definition. |
| SAP BW | A process chain looks complete in the scheduler but the expected output is late. | Trace the BW chain run and the dependent process or data load. Ask the application owner which BW execution produced the business result. |
| JD Edwards AIS / UBE | Two runs of the same report finish close together. | Link the submission to its JDE job number, then link that number to the output. Confirm which document reached its destination. |
| Informatica | A second workflow start reports that a run is already active. | Correlate scheduler run, repository/folder/workflow and business period. A duplicate trigger and a legitimate next period require different recovery decisions. |
| Queues and process servers | Jobs accumulate when one server goes down. | Check whether another eligible process server can accept the queue, the oldest waiting job and whether backlog is growing. Route infrastructure impact and job failures to the appropriate owners. |
| Time windows and submit frames | A close process runs one business day early. | Compare business date, time zone, calendar revision and evaluated occurrences. Test a holiday at month end and trace the first run after a closed window. |
| Locks and events | A chain stays active without visible progress. | Identify the waiting child, outstanding condition, producer or lock holder and the exact parent run. Verify in the native Process view. |
| Access to assigned workflows | A business user should monitor one chain and submit another. | Test two ordinary users, a copied native link, an expired assignment and an execution with no history. Test application display and scheduler privileges separately. |
| SLA and handover | A late chain leaves support with no next action. | Record the business deadline, current blocker, last confirmed execution or external receipt, and the role authorised to act. Carry the same references into the incident. |

[Explore the migration controls](migration-field-guide.md) · [See a filled cutover handover](cutover-handover.md)

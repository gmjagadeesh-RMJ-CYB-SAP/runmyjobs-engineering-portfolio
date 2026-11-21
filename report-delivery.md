# Delivering RunMyJobs reports to SharePoint

In July 2026 I worked on distributing existing RMJ usage and counted-job reports. The report generation already existed. My work picked up its output and carried it through an RMJ email and a Power Automate flow to a SharePoint destination.

| Step | What mattered |
| --- | --- |
| Select the RMJ output | Identify the generated report attachment among the job outputs. |
| Prepare the attachment | Apply the environment and date to the filename in a separate workflow step. |
| Send through RMJ | Deliver the chosen attachment to the receiving inbox. |
| Process it in Power Automate | Use the attachment fields from the actual message and route the file to the intended SharePoint location. |

Testing confirmed email delivery and the first flow. I have no recorded destination result for the second report route. I would keep that route open until a specific source report can be matched to its file at the intended destination.

A practical review starts with one report run. Record its selected output, received attachment name and final folder entry. Where filenames can recur, compare the file content or another stable identifier as well. An inbox receipt gives an operator a good midpoint from which to investigate a missing file.

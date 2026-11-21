# Moving RunMyJobs release artefacts through Azure DevOps

In May and June 2025 I worked on two release paths. Each moved a different artefact. Keeping those artefacts explicit was important when we reviewed what the pipeline had actually demonstrated.

| Direction | Artefact | Engineering work |
| --- | --- | --- |
| RMJ to Azure Repos | XML | Selected the object and related objects for promotion, then the destination repository and branch. |
| Azure Pipelines to RMJ | An existing binary CAR archive | Checked out the repository, checked that the file existed, and used a Windows PowerShell task to upload the archive. |

I worked on ruleset handling, pipeline variables, response logging and failure exits. The working upload established that the pipeline could send the archive. Import validation remained limited. The work did not demonstrate automatic packaging of the exported XML into a CAR.

## What I would look for in a release review

A useful release record ties the repository revision to the intended CAR and target. I would inspect the upload response, then the import result for that archive and ruleset. To close a finding about related objects, I would check the affected definitions in the intended target and record which dependencies resolved. A successful pipeline step answers only the stage that emitted it.

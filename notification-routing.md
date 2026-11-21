# Routing failure emails and ServiceNow incidents

I worked on several variants of a notification workflow. Redwood supplied the ServiceNow connector. My work placed routing around it so that each implementation could choose the recipients, incident metadata and notification channels from configuration.

| Decision | Design consideration |
| --- | --- |
| Which channel should run? | Keep email and incident switches independent. A rule can enable one or both. |
| Where should the notification go? | Read the recipients and incident metadata from the relevant table entry. |
| What should the recipient investigate? | Carry the job and execution context into the notification. |
| Which workflow level should notify? | Handle child-job routing so that the parent does not issue a duplicate notification for the same failure. |

Tests produced email and ServiceNow incidents. Later variants introduced different restart and throttling requirements. Their behaviour needs evidence tied to the specific version.

For example, if incident creation succeeds and email delivery fails, a replay raises a concrete question. Can the operator identify the incident already created for that execution before replaying the failed channel? I would include the incident reference, channel result and execution reference in that review. This is a proposed test scenario.

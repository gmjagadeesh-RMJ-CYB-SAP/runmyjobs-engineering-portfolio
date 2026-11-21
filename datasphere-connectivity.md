# Diagnosing a SAP Datasphere connector connection

I investigated a Datasphere and authentication-service connection by checking each boundary in order. The retained results narrow the next investigation to the application layer.

| Check | Recorded observation | What that establishes |
| --- | --- | --- |
| DNS | The tested service names resolved. | Name resolution worked for those names from the test location. |
| TCP | Connections to the tested port were established. | The tested host and port were reachable from that location. |
| TLS | The tested handshake completed. | That client and endpoint completed the handshake during the check. |
| OAuth / business request | A successful application result remained unverified. | Token issuance and the intended Datasphere operation still needed their own evidence. |

For the handover, I would record which client and endpoint produced each observation. A workstation and an RMJ execution host may use different network paths or trust stores. To close the case, the evidence I would look for is a token response from the intended runtime and the status of the authorised business request. Diagnostic notes can capture status, time and a correlation reference while keeping token values private.

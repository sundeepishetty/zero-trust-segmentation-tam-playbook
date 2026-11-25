# Containing risk on an exposed web tier

**Tabletop exercise.** A customer receives a critical advisory concerning its internet-facing NGINX tier. A legacy application constrains an immediate OS upgrade. The incident lead must establish exposure, limit unnecessary reachability and preserve the customer service while the platform owner validates a supported fix.

| Decision | Owner and evidence |
| --- | --- |
| Which systems are affected? | Platform owner checks the actual package build, package source, enabled features and point of protocol termination against the upstream advisory and distribution notice. Record affected, unaffected and unknown hosts separately. |
| Is there evidence of compromise? | SOC reviews available edge, host and network telemetry, preserves evidence and follows the incident-response process for suspected compromise. Record the time range and visibility gaps. |
| What can we contain now? | Network owner restricts direct access to origins to the approved ingress tier where appropriate. Review web-tier egress and east-west rules against required application, monitoring and management flows. Isolate suspected hosts with the incident lead and move traffic to validated healthy capacity where available. |
| What can the segmentation platform add? | On covered hosts, review observed dependencies, effective policy and enforcement state. Scope a change to the affected cohort. Verify required paths and a denied unnecessary path. Where coverage is missing, assign the existing firewall or cloud network control to an owner. |
| What addresses the vulnerable component? | Platform owner checks the distributor's fixed build, support entitlement and repository coverage for the installed package. If a fix is available, canary it under representative traffic. If one is pending, assess vendor-documented workarounds and give temporary controls an owner, expiry and review date. |
| When is service safe to expand? | Application owner signs off health checks, critical transactions and scheduled reconciliation. Operations verifies the running fixed build or records residual exposure. If a canary fails, drain it, maintain containment and reassess with the change owner. |

**First customer update.** “We are checking which exposed systems are affected and whether there are signs of compromise. The network team is reviewing immediate containment while the application owner checks service impact. I’ll update you in 15 minutes with confirmed scope, action owners and the next decision.”

**Closure evidence.** Record containment coverage and patch coverage separately. Track outstanding exceptions to expiry, prioritise migration of unsupported components and ask the service owner to validate recovery. A successful network restriction reduces reachability while the vulnerable software still needs remediation.

[NGINX security advisories](https://nginx.org/en/security_advisories.html) · [Ubuntu security notices](https://ubuntu.com/security/notices)

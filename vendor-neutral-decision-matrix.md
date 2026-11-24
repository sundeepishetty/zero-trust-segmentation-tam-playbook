# Vendor-neutral decision matrix

This is not a feature battlecard. It is a discovery framework for understanding which segmentation approach best fits a customer’s estate and operating model.

| Decision area | Questions to test | Customer evidence required |
| --- | --- | --- |
| Business outcome | Is the priority ransomware containment, compliance, M&A isolation, cloud consistency or OT protection? | Risk assessment, regulatory scope, resilience objectives |
| Estate coverage | Which servers, endpoints, containers, cloud services, legacy or unmanaged assets require visibility and enforcement? | Asset inventory and ownership |
| Enforcement model | Where can host agents, native controls, network controls or agentless methods be used safely? | Platform standards and operational constraints |
| Application context | How accurately can workloads and flows be associated with business applications and owners? | CMDB, cloud tags, dependency maps and owner validation |
| Policy lifecycle | How will policy be modelled, tested, approved, enforced and rolled back? | Change-management and exception processes |
| Operations | Which teams own platform health, policy changes, incidents and application onboarding? | RACI and support model |
| Integrations | Which SIEM, SOAR, ITSM, identity, cloud and firewall workflows are material? | Architecture and operational use cases |
| Value measurement | What evidence will demonstrate reduced risk and sustained adoption? | Success plan, baseline and QBR measures |

## Market vendor comparisons

Give each vendor the same two workload IDs, dependency and recovery scenario. Record the product version, supported operating system and evidence from the demonstration before scoring.

| Candidate | What to demonstrate on the payment pilot | Evidence to retain |
| --- | --- | --- |
| [Illumio](https://product-docs-repo.illumio.com/Tech-Docs/Core/PDFs/Security_Policy_25_2.pdf) | Show how workload labels resolve to R004 and where selective enforcement applies. | Policy preview, effective scope and rollback record |
| [Akamai Guardicore Segmentation](https://www.akamai.com/products/akamai-guardicore-segmentation) | Trace the payment dependency in the application map and show what happens when a workload moves. | Before-and-after map, coverage gaps and owner validation |
| [Cisco Secure Workload](https://www.cisco.com/site/us/en/products/security/secure-workload/index.html) | Show how observed dependencies inform policy and which control enforces it on each pilot platform. | Flow evidence, enforcement location and recovery test |

For each candidate record **demonstrated**, **partially demonstrated** or **unverified** against the same acceptance test. Ask the customer which remaining gap carries the greatest operational cost.

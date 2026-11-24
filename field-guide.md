# Reading the workload inventory and policy matrix

One workload row describes an asset. One policy row describes a directional business dependency or restriction. Use [workloads.csv](workloads.csv) for asset counts and [policy-matrix.csv](policy-matrix.csv) for rule counts.

## What does enforcement_stage mean?

It records how far the **customer** has taken a workload through its adoption process. The deployment team records the actual platform mode and effective scope separately at change time. Two hosts can be at the same project stage and have different effective policies.

| Value | What is true at this stage | Evidence needed to progress |
| --- | --- | --- |
| Observe | Collect ownership and flow history while the team learns the service. | Baseline includes routine and infrequent jobs, with unknowns listed. |
| Model | Draft intended connections between labelled workloads. | Each proposed path has a purpose, direction and service. |
| Validate | The application owner checks expected and unexpected paths against the draft. | Recorded tests, dependencies, exceptions and owner sign-off. |
| Stage | A limited rollout is underway for a named service or cohort. | Record the effective scope, business checks and rollback result before expanding. |
| Enforce | The approved scope has entered normal operation. | Operations monitors drift, exceptions and service health and can restore the previous policy. |

The rule column **stage** uses the same sequence at the level of one rule. **Proposed** means someone has raised the intent and it awaits scoping. R009 therefore describes a desired denial. The CSV alone cannot prove that traffic was blocked.

## Workload fields

| Field | How to read the values |
| --- | --- |
| workload_id / hostname | Stable W-number for cross-references / illustrative host name for operators. Two hosts can serve the same application tier. |
| role | Web serves the front end, API receives service calls, Application runs business or ETL logic, Database stores records, Management brokers administration, Security supports monitoring, Integration exchanges data with a partner. |
| application | CustomerPortal serves digital channels, PolicyAdmin services insurance policies, Payments supports settlement, Analytics processes data, SharedServices provides common infrastructure, SecurityOperations supports the SOC, PartnerExchange handles partner transfers. |
| environment | Production serves live business activity. UAT supports user acceptance testing. |
| location | DataCentre denotes the on-premises estate. Azure-UK and AWS-UK denote the respective UK cloud environments. |
| criticality | Critical means loss materially interrupts a key service or control. High means significant dependency with a narrower impact. Medium denotes a lower-impact test or supporting tier in this example. |
| owner | Team accountable for validating the workload and approving its dependencies. |
| crown_jewel / business_impact | Yes marks an asset selected for explicit protection against material business loss. No identifies a supporting asset. The impact column explains the selection. Includes W006 for policy records and W008 for payment reconciliation. |

## Policy fields and worked example

| Field | Meaning |
| --- | --- |
| rule_id | Stable R-number used in approvals and test evidence. |
| consumer / provider | Initiating workload group / destination providing the service. Group membership must be resolved before rollout. |
| service / port | Intended service and destination port. “or” lists alternatives requiring separate scoping. Any covers all services in the proposed UAT denial. |
| environment | Production means a production flow. Cross means the rule crosses an environment boundary. |
| business_justification / owner | Why the business needs this decision / team accountable for validation. |
| decision / stage | Allow or Deny describes intent. Stage describes the progress of the rule review and rollout. |
| crown_jewel_scope | Direct identifies a named database destination. Indirect identifies a dependency of its application. Candidate indicates broad group membership requiring review. None means no named crown jewel in that rule. |
| validation_evidence | Acceptance check to collect. The entry describes a test, and its result belongs in the change record. |

**Read R004 aloud.** W007 initiates a payment transaction to W008 on TCP 1433. W008 is a crown jewel because its records support settlement reconciliation. R004 is at Stage. Before expanding, capture one successful payment, reconciliation, and a denied connection from a workload with no approved dependency. The Payments owner confirms the business result and Database Services confirms the policy evidence.

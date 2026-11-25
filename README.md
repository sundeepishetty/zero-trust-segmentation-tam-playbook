# Kairos Yukton | Zero Trust Segmentation TAM Playbook

Kairos Yukton is a fictional UK insurer with on-premises payment and policy systems, an Azure customer portal and AWS analytics. Its payments director wants to limit access to settlement records while keeping payments and month-end reconciliation running. This worked example shows how a technical account manager helps the customer decide when to enforce a boundary and how to measure the result. All assets, policies and metrics are illustrative.

## Follow one payment

1. Find the payments application **W007** and its database **W008** in the [workload inventory](workloads.csv). W008 is a crown jewel because its records support settlement reconciliation.
2. Read **R004** in the [policy matrix](policy-matrix.csv). The application initiates the approved database connection. The [field guide](field-guide.md) defines the owner, stage and evidence recorded for each rule.
3. Follow the path on the [architecture diagram](target-architecture.md). The application owner validates business dependencies before the change owner approves a limited rollout.
4. Open the [quarterly scorecard](qbr-scorecard.md). Two of fifteen workloads are in routine enforcement. Both crown jewels still need validation before the sponsor can count them as protected across the intended scope.

## Two customer decisions

**A connection appears only at month-end.** Finance and the Payments owner trace the scheduled job and review what the proposed rule would block. Hold changes affecting the uncertain path until the owner validates the dependency. Progress an independent rule only if its impact and rollback have been tested separately. Capture a successful payment, completed reconciliation and a denied unauthorised path before expanding the pilot.

**A critical advisory affects the internet-facing web tier.** The incident lead needs a decision while the application team validates the fix. The [web-tier containment exercise](web-tier-containment.md) covers the first customer update, network controls already available, patch qualification and recovery evidence.

## Running the engagement

| Customer need | Working document |
| --- | --- |
| Agree owners, milestones and pilot exit criteria | [90-day adoption plan](90-day-adoption-plan.md) |
| Route operational issues and sponsor decisions | [Engagement cadence](engagement-cadence.md) |
| Coordinate a service incident and verify recovery | [Escalation runbook](escalation-runbook.md) |
| Compare suppliers against the same acceptance tests | [Market vendor comparisons](vendor-neutral-decision-matrix.md) |
| Check product terminology and standards | [References](references.md) |

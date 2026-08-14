# CNAPP Alert Triage — Design Write-up

## Proposed Flow

The proposed experience helps a security engineer move from a large alert queue to the right remediation with minimal investigation and context-switching.

**1. Alert Queue:** A filterable and prioritized alert list across cloud accounts, with summary metrics for quickly understanding the overall security posture.

**2. Alert Detail / Investigation:** Provides plain-language context on why an alert was flagged, the affected resource, compliance impact, blast radius, and actions such as assign, snooze, or dismiss.

**3. Remediation & Close-out:** Provides one-click auto-remediation for well-understood low-risk fixes, manual remediation steps for other cases, an exception path, and an audit trail.

## Feature Prioritization

Using a **MoSCoW framework**:

**Must Have — v1**

* Filterable alert queue by severity, account, cloud provider, and status
* Alert detail with plain-language explanation and affected resource
* Assign, snooze, and false-positive actions
* Basic audit trail

**Should Have — v1.1**

* Blast-radius and related-resource context
* Compliance framework mapping
* Manual remediation guidance

**Could Have — v2**

* One-click auto-remediation for curated low-risk issues
* Exception/allowlist workflow with expiry
* Similar-alert clustering

**Won't Have Yet**

* Fully autonomous remediation without human approval

### Prioritization Rationale

The alert queue and detail view are the foundation of the workflow. Blast radius and compliance context help reduce the time required to determine whether an alert is genuinely urgent. Auto-remediation is intentionally introduced later because incorrect automated fixes can impact production systems, so trust should first be built through clear explanations, human approval, and auditability.

## Success Metrics

* **Mean Time to Triage:** Target 40% reduction in time from alert creation to first action.
* **Mean Time to Resolution:** Reduce the time from triage to remediation or closure.
* **Critical Alerts Resolved Within SLA:** Increase the percentage resolved within the defined SLA, such as 4 hours.
* **False-Positive Dismissal Rate:** Maintain or reduce the rate as detection quality improves.
* **Auto-Remediation Adoption:** Measure the percentage of eligible alerts resolved through one-click remediation in v2.

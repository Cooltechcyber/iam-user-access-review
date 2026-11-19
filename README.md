# IAM User Access Review & Access Certification

Hands-on **Identity and Access Management (IAM)** security analyst portfolio lab using **Windows Server 2022 Active Directory** and **PowerShell**. Demonstrates departmental access discovery, least-privilege review, simulated certification, removal of excessive group membership, and post-remediation validation.

> **Training environment only.** All employees, tickets, and review approvals are fictional. This project is on-premises Active Directory; no Microsoft Entra ID synchronization or application-level permission validation is claimed.

## Scenario: IAM-UAR-001 — Excessive Finance group membership

A simulated quarterly access review found **Michael Johnson** (`mjohnson`), an IT Support Specialist in Information Technology, in both `SG-IT-Users` and `SG-Finance-Users`. The Finance membership was deliberately introduced for this lab and was not supported by the scenario's approved departmental access baseline.

**Simulated access owner decision:** Revoke `SG-Finance-Users`; retain `SG-IT-Users`.

**Verified outcome:** After removal, PowerShell returned `Domain Users` and `SG-IT-Users` only. The user remained enabled in Information Technology.

## Review workflow

1. **Inventory:** Enumerate users, account state, and departmental security groups.
2. **Baseline:** Confirm approved memberships for IT, HR, and Finance employees.
3. **Detect:** Identify an intentionally added Finance membership for an IT employee.
4. **Certify (simulated):** Record a revoke decision and business justification.
5. **Remediate:** Remove the inappropriate Finance membership.
6. **Validate:** Confirm the employee retains authorized IT membership and the account remains enabled.

## Lab scope

| Component | Details |
| --- | --- |
| Domain | `COOLTECHLAB.COM` |
| Server | Windows Server 2022 domain controller (DC01) |
| Users OU | `OU=Users,OU=IAM-Lab,DC=COOLTECHLAB,DC=COM` |
| Groups OU | `OU=Groups,OU=IAM-Lab,DC=COOLTECHLAB,DC=COM` |
| Groups | `SG-IT-Users`, `SG-HR-Users`, `SG-Finance-Users` |
| Tools | Active Directory PowerShell module |

## Evidence gallery — pending screenshot upload

| Evidence | Screenshot |
| --- | --- |
| Account inventory | [01 — Existing users](screenshots/01-uar-existing-users.png) |
| Group inventory | [02 — Security groups](screenshots/02-uar-security-groups.png) |
| Authorized baseline | [03 — Current memberships](screenshots/03-uar-current-memberships.png) |
| Finding: IT user attributes | [04 — User attributes](screenshots/04-uar-excessive-access-user-attributes.png) |
| Finding: excessive Finance group | [05 — Excessive membership](screenshots/05-uar-excessive-access-group-membership.png) |
| Remediation: account still enabled | [06 — Account status](screenshots/06-uar-after-remediation-user-status.png) |
| Remediation: Finance membership removed | [07 — Group membership](screenshots/07-uar-after-remediation-group-membership.png) |

**Case study:** [IAM-UAR-001 — User Access Review](docs/IAM-UAR-001-access-review.md)

**Access certification record:** [Simulated certification decision](docs/IAM-UAR-001-certification-record.md)

## Security concepts demonstrated

Identity inventory · Role-based group assignment · Least privilege · Access recertification · Excessive access detection · Access removal · PowerShell verification · Audit evidence

## Limitations

The verified results concern **AD account attributes and group memberships**. No file-share, application, cloud, or session-level access tests were performed. A simulated reviewer decision is not a production approval. Screenshot links will resolve after the evidence is uploaded.

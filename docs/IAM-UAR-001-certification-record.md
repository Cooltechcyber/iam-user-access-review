# IAM-UAR-001 — Simulated Access Certification Record

> **Fictional training record.** This is not evidence of a production review or a real manager's approval.

| Field | Recorded value |
| --- | --- |
| Review | IAM-UAR-001 |
| Review type | Simulated quarterly departmental access certification |
| Identity | Michael Johnson (`mjohnson`) |
| Employee role | IT Support Specialist, Information Technology |
| Access under review | `SG-Finance-Users` |
| Authorized group to retain | `SG-IT-Users` |
| Reviewer role | Simulated Finance resource owner |
| Decision | **Revoke** Finance membership |
| Reason | No documented business justification for Finance membership under the fictional approved baseline |
| Action | Remove `mjohnson` from `SG-Finance-Users` |
| Verification | `Domain Users` and `SG-IT-Users` returned; `SG-Finance-Users` absent |
| Outcome | **AD group-level remediation verified** |

## Control considerations

- **Least privilege:** Remove memberships not justified by the defined job role.
- **Separation of duties:** A production reviewer should be authorized to certify access, independently of the person making the change as appropriate.
- **Audit trail:** Preserve the baseline, finding, decision, change, and post-change evidence.
- **Limitations:** No effective Finance resource access test or live reviewer attestation was performed.

# Access Control Worksheet

**Incident summary:** A deposit was made from the business to an unknown bank account. The finance manager confirmed they did not authorize the transaction. The payment was stopped in time, but an investigation is underway to identify the threat actor and prevent future incidents.

---

| **Column** | **Details** |
|---|---|
| **Notes** | 1. The event log shows the payroll event originated from IP address `152.207.255.255`, logged under the user `Legal\Administrator` on the computer named `Up2-NoGud`. Cross-referencing the employee directory reveals this IP address belongs to **Robert Taylor Jr.**, a legal attorney who worked as a contractor. <br><br> 2. Robert Taylor Jr.'s end date in the employee directory is listed as `43826.0` (approximately March 2020), meaning his contract ended years before the incident on 10/03/2023. Despite no longer being with the company, his credentials and access were apparently still active, allowing him to log in and initiate the payroll event. |
| **Issue(s)** | 1. **Access was not revoked after the contractor's end date.** Robert Taylor Jr.'s employment ended years prior, yet his account remained active with Admin-level authorization. This is a direct violation of least privilege — former employees and contractors should have access immediately revoked upon departure. <br><br> 2. **All employees share the same authorization level (Admin).** The employee directory shows every person — from the owner and security analyst to seasonal sales associates and part-time marketers — is granted Admin access. This means any compromised account, including a former contractor's, has full system privileges. Users should only have access appropriate to their role. |
| **Recommendation(s)** | 1. **Implement a formal offboarding process that immediately revokes system access.** When a contractor or employee's end date is reached, their accounts, credentials, and permissions should be automatically disabled or deleted. Regular audits of the employee directory against active accounts should be scheduled to catch any oversights. <br><br> 2. **Enforce role-based access control (RBAC) using the principle of least privilege.** Each employee should be granted only the access level their role requires — a graphic designer or seasonal sales associate should not hold Admin privileges. Creating tiered permission levels (e.g., Admin, Editor, Viewer) reduces the blast radius of any single compromised account. |

---

## Supporting Evidence

### Event Log

| Field | Value |
|---|---|
| Event Type | Information |
| Event Source | AdsmEmployeeService |
| Event ID | 1227 |
| Date | 10/03/2023 |
| Time | 8:29:57 AM |
| User | Legal\Administrator |
| Computer | Up2-NoGud |
| IP Address | 152.207.255.255 |
| Description | Payroll event added. FAUX_BANK |

### Employee Directory (Relevant Entry)

| Name | Role | Email | IP Address | Status | Authorization | End Date |
|---|---|---|---|---|---|---|
| Robert Taylor Jr. | Legal attorney | rt.jr@erems.net | 152.207.255.255 | Contractor | Admin | 43826.0 (expired) |
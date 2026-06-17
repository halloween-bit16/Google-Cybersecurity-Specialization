# Data Leak Worksheet

**Incident summary:** A sales manager shared access to a folder of internal-only documents with their team during a meeting. The folder contained files associated with a new product that has not been publicly announced. It also included customer analytics and promotional materials. After the meeting, the manager did not revoke access to the internal folder, but warned the team to wait for approval before sharing the promotional materials with others.

During a video call with a business partner, a member of the sales team forgot the warning from their manager. The sales representative intended to share a link to the promotional materials so that the business partner could circulate the materials to their customers. However, the sales representative accidentally shared a link to the internal folder instead. Later, the business partner posted the link on their company's social media page assuming that it was the promotional materials.

---

| **Control** | **Least Privilege** |
|---|---|
| **Issue(s)** | The manager failed to revoke access to the internal folder after the meeting, violating the principle of least privilege by leaving the sales representative with broader access than needed. The representative then accidentally shared a link to the entire internal folder instead of just the promotional materials, exposing confidential documents to an external business partner who posted them publicly on social media. |
| **Review** | NIST SP 800-53: AC-6 defines the principle of least privilege, requiring that users, processes, and roles be granted only the minimal access necessary to perform their assigned tasks. It emphasizes enforcing access controls to prevent users from operating at privilege levels beyond what their business objectives require. Control enhancements include restricting access by user role, automatically revoking access after a set period, maintaining activity logs, and regularly auditing user privileges. |
| **Recommendation(s)** | 1. Restrict access to sensitive resources based on user role — sales representatives should only be granted access to approved promotional materials, not internal folders containing confidential data such as customer analytics or unannounced product plans. <br><br> 2. Automatically revoke access to information after a defined period of time — shared folder permissions should expire automatically following a meeting or event, ensuring that temporary access does not remain open indefinitely due to human oversight. |
| **Justification** | Restricting folder access by user role would have prevented the sales representative from ever having access to the confidential internal documents in the first place, meaning a mistakenly shared link could only have exposed approved materials. Implementing automatic access expiration would have served as a safety net to close any permissions that managers forget to revoke, removing reliance on manual processes that are vulnerable to human error. |

---

## Security Plan Snapshot

The NIST Cybersecurity Framework (CSF) uses a hierarchical, tree-like structure to organize information. From left to right, it describes a broad security function, then becomes more specific as it branches out to a category, subcategory, and individual security controls.

| **Function** | **Category** | **Subcategory** | **Reference(s)** |
|---|---|---|---|
| **Protect** | PR.DS: *Data security* | PR.DS-5: *Protections against data leaks.* | NIST SP 800-53: AC-6 |

---

## NIST SP 800-53: AC-6

NIST developed SP 800-53 to provide businesses with a customizable information privacy plan. It's a comprehensive resource that describes a wide range of control categories. Each control provides a few key pieces of information:

- **Control:** A definition of the security control.
- **Discussion:** A description of how the control should be implemented.
- **Control enhancements:** A list of suggestions to improve the effectiveness of the control.

| **AC-6** | **Least Privilege** |
|---|---|
| | **Control:** Only the minimal access and authorization required to complete a task or function should be provided to users. |
| | **Discussion:** Processes, user accounts, and roles should be enforced as necessary to achieve least privilege. The intention is to prevent a user from operating at privilege levels higher than what is necessary to accomplish business objectives. |
| | **Control enhancements:** Restrict access to sensitive resources based on user role. Automatically revoke access to information after a period of time. Keep activity logs of provisioned user accounts. Regularly audit user privileges. |
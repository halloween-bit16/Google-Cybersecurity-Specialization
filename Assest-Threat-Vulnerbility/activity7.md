# Parking Lot USB Exercise
**Rhetorical Hospital – Security Assessment**

---

## Contents

The USB drive contains a mix of personal and professional files belonging to Jorge Bailey, the HR manager at Rhetorical Hospital. Personal files include family photos, pet pictures, a wedding list, and vacation ideas, while work-related files include a new hire letter, employee shift schedules, an annual budget tracker, and Jorge's resume. Together, these files reveal significant amounts of both personally identifiable information (PII) and sensitive organizational data.

---

## Attacker Mindset

An attacker who obtained this drive could use Jorge's resume and HR role to craft convincing spear-phishing emails targeting hospital staff, or use the shift schedule to identify when specific employees are on-site. The new hire letter and budget files could expose internal processes and financial data, giving an attacker enough context to impersonate hospital management or manipulate new employees before they've learned security protocols.

---

## Risk Analysis

From a technical standpoint, the hospital should implement endpoint controls that disable auto-run features and restrict unauthorized USB devices from connecting to workstations. Operationally, employees should be trained to never plug in unrecognized USB drives and to report found devices to the security team immediately. Managerially, the hospital should establish a clear acceptable use policy that prohibits storing sensitive work files on personal or unencrypted drives. Using virtualization software — as was done here — is an important technical safeguard when investigating suspicious media safely.
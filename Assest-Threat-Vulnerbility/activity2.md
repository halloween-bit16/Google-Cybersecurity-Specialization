### Notes (Risk Factors)

The bank handles sensitive financial data for thousands of customers using both on-premises and remote employees, increasing the risk of phishing attacks, database compromises, and data leaks. Because the bank operates in a coastal area and must meet strict financial regulations, natural disasters, theft, and supply chain disruptions could impact the availability of funds and critical services. Regulatory penalties and reputational damage could significantly affect the bank if these risks are not properly managed.

---

## Completed Risk Register

| Asset | Risk(s)                   | Likelihood (1-3) | Severity (1-3) | Priority (Likelihood × Severity) |
| ----- | ------------------------- | ---------------- | -------------- | -------------------------------- |
| Funds | Business email compromise | **3**            | **3**          | **9**                            |
| Funds | Compromised user database | **2**            | **3**          | **6**                            |
| Funds | Financial records leak    | **2**            | **3**          | **6**                            |
| Funds | Theft                     | **1**            | **3**          | **3**                            |
| Funds | Supply chain disruption   | **1**            | **2**          | **2**                            |

---

### Justification

| Risk                      | Reasoning                                                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Business email compromise | Many employees handle financial data, making phishing attacks relatively common. Successful compromise could lead to fraud and financial losses. |
| Compromised user database | Banks are frequent cyberattack targets. Exposure of customer data would have serious regulatory and reputational consequences.                   |
| Financial records leak    | Sensitive financial information is highly valuable. A leak could result in fines, lawsuits, and loss of customer trust.                          |
| Theft                     | The area has low crime rates, reducing likelihood, but theft of funds would still have a major impact.                                           |
| Supply chain disruption   | Coastal location increases exposure to hurricanes and weather-related disruptions, though such events are relatively infrequent.                 |

### Final Scores

| Risk                      | Likelihood | Severity | Priority |
| ------------------------- | ---------- | -------- | -------- |
| Business email compromise | 3          | 3        | **9**    |
| Compromised user database | 2          | 3        | **6**    |
| Financial records leak    | 2          | 3        | **6**    |
| Theft                     | 1          | 3        | **3**    |
| Supply chain disruption   | 1          | 2        | **2**    |

**Highest priority:** Business email compromise (9)
**Medium priority:** Compromised user database (6), Financial records leak (6)
**Lower priority:** Theft (3), Supply chain disruption (2)

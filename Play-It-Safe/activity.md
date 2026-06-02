# Botium Toys Internal Security Audit

## Controls Assessment Checklist

| Control                                                             | Yes | No |
| ------------------------------------------------------------------- | --- | -- |
| Least Privilege                                                     |     | ✅  |
| Disaster Recovery Plans                                             |     | ✅  |
| Password Policies                                                   | ✅   |    |
| Separation of Duties                                                |     | ✅  |
| Firewall                                                            | ✅   |    |
| Intrusion Detection System (IDS)                                    |     | ✅  |
| Backups                                                             |     | ✅  |
| Antivirus Software                                                  | ✅   |    |
| Manual Monitoring, Maintenance, and Intervention for Legacy Systems | ✅   |    |
| Encryption                                                          |     | ✅  |
| Password Management System                                          |     | ✅  |
| Locks (Offices, Storefront, Warehouse)                              | ✅   |    |
| Closed-Circuit Television (CCTV) Surveillance                       | ✅   |    |
| Fire Detection/Prevention Systems                                   | ✅   |    |

---

## Compliance Checklist

### Payment Card Industry Data Security Standard (PCI DSS)

| Best Practice                                                                                              | Yes | No |
| ---------------------------------------------------------------------------------------------------------- | --- | -- |
| Only authorized users have access to customers' credit card information                                    |     | ✅  |
| Credit card information is stored, accepted, processed, and transmitted internally in a secure environment |     | ✅  |
| Implement data encryption procedures to secure credit card transaction touchpoints and data                |     | ✅  |
| Adopt secure password management policies                                                                  |     | ✅  |

---

### General Data Protection Regulation (GDPR)

| Best Practice                                                                     | Yes | No |
| --------------------------------------------------------------------------------- | --- | -- |
| E.U. customers' data is kept private/secured                                      | ✅   |    |
| There is a plan to notify E.U. customers within 72 hours of a breach              | ✅   |    |
| Ensure data is properly classified and inventoried                                |     | ✅  |
| Enforce privacy policies, procedures, and processes to document and maintain data | ✅   |    |

---

### System and Organizations Controls (SOC 1 / SOC 2)

| Best Practice                                                                | Yes | No |
| ---------------------------------------------------------------------------- | --- | -- |
| User access policies are established                                         |     | ✅  |
| Sensitive data (PII/SPII) is confidential/private                            |     | ✅  |
| Data integrity ensures data is consistent, complete, accurate, and validated | ✅   |    |
| Data is available to authorized individuals                                  | ✅   |    |

---

## Recommendations

### High Priority

1. Implement least privilege and separation of duties controls immediately to restrict employee access to sensitive customer and cardholder data.
2. Deploy encryption for all stored, processed, and transmitted credit card information.
3. Install and configure an Intrusion Detection System (IDS) to detect suspicious network activity.
4. Create and test disaster recovery and business continuity plans.
5. Implement regular backups of critical business and customer data.

### Medium Priority

1. Deploy a centralized password management system.
2. Strengthen password requirements to meet modern security standards.
3. Establish a formal schedule and documented procedures for monitoring and maintaining legacy systems.
4. Complete asset inventory and classification efforts to align with NIST CSF Identify functions.

### Low Priority

1. Continue maintaining existing firewall and antivirus solutions.
2. Continue enforcing privacy policies and GDPR breach notification procedures.
3. Maintain physical security controls including locks, CCTV surveillance, and fire detection/prevention systems.

---

## Overall Audit Conclusion

Botium Toys currently has several important technical and physical security controls in place, including a firewall, antivirus software, CCTV surveillance, locks, and fire protection systems. However, the company faces significant cybersecurity and compliance risks due to inadequate access controls, lack of encryption, absence of backups and disaster recovery planning, and incomplete adherence to PCI DSS requirements. The organization's current risk score of 8/10 accurately reflects its elevated risk exposure. Immediate remediation of access control, encryption, backup, and monitoring deficiencies is recommended to improve the company's security posture and regulatory compliance.

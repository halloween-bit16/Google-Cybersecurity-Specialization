# PASTA Threat Model Worksheet
**Application: Sneaker Company Mobile App**

---

## Stage I — Define Business and Security Objectives

- The app must securely process financial transactions, including multiple payment options, while complying with relevant data privacy regulations (e.g., PCI-DSS for payment card data).
- User accounts must be protected with strong authentication, and all personal data must be stored and handled responsibly to maintain customer trust.
- The platform must support seamless buyer-seller communication, ratings, and inventory listings, while ensuring that data privacy policies are enforced throughout every interaction.

---

## Stage II — Define the Technical Scope

**Technologies used by the application:**
- API
- PKI (AES + RSA encryption)
- SHA-256
- SQL

**Priority technology — SQL:**

SQL would be the first technology to evaluate because it directly interacts with sensitive user and product data, including payment details and seller information. SQL databases are a frequent target for injection attacks, which could expose or corrupt the entire data store. A breach here would have the highest business and legal impact.

---

## Stage III — Decompose Application

**Data Flow Diagram Summary:**

The data flow diagram illustrates a product search process involving three components:

```
User  →  Product Search Process  →  Database
         ← Listings of current inventory ←
```

A user submits a search query for sneakers. The request is passed to the product search process, which queries the database. The database returns current inventory listings back through the process to the user.

> Note: This diagram represents a single process. Full application data flow diagrams are considerably more complex.

---

## Stage IV — Threat Analysis

**Two identified threats:**

1. **SQL Injection (External Threat):** A threat actor could exploit improperly sanitized input fields in the app to inject malicious SQL commands, potentially accessing, modifying, or deleting the entire database of user and product data.

2. **Session Hijacking (External/Internal Threat):** An attacker could intercept or steal session tokens — especially if weak login credentials are in use — to impersonate legitimate users and gain unauthorized access to accounts and payment information.

---

## Stage V — Vulnerability Analysis

**Two identified vulnerabilities:**

1. **Lack of Prepared Statements (Codebase Weakness):** If SQL queries are constructed by directly embedding user input rather than using parameterized/prepared statements, the database becomes vulnerable to injection attacks. This is a common coding flaw that can expose the entire database.

2. **Weak Login Credentials (Authentication Weakness):** If the app does not enforce strong password policies or multi-factor authentication (MFA), users may rely on easy-to-guess credentials, making session hijacking and brute-force attacks significantly easier for attackers.

---

## Stage VI — Attack Modeling

**Attack Tree Summary:**

```
Target: User Data
│
├── SQL Injection
│   └── Lack of prepared statements
│
└── Session Hijacking
    └── Weak login credentials
```

> Note: A production-level application would have a much larger, more complex attack tree with many additional branches and attack paths.

---

## Stage VII — Risk Analysis and Impact

**Four security controls to reduce risk:**

1. **Prepared Statements / Parameterized Queries:** Enforce the use of prepared statements for all database interactions to prevent SQL injection attacks from succeeding, regardless of what input a user or attacker provides.

2. **Multi-Factor Authentication (MFA):** Require users to verify their identity through a second factor (e.g., SMS code or authenticator app) in addition to their password, significantly reducing the risk of account takeover via session hijacking or credential theft.

3. **Data Encryption (AES + RSA via PKI):** Encrypt all sensitive data in transit and at rest using the app's existing PKI framework. This ensures that even if data is intercepted or a breach occurs, it remains unreadable to unauthorized parties.

4. **SHA-256 Password Hashing:** Store user passwords using SHA-256 (or a stronger algorithm like bcrypt) so that plaintext credentials are never stored in the database, limiting the damage caused by any potential data breach.
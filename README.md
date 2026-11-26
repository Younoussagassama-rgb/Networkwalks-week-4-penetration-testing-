# NetworkWalks — Week 4: Reconnaissance & SQL Injection Lab

## 📌 Overview
This repository documents **Week 4** of my NetworkWalks hands-on cybersecurity training. The focus of this week was **reconnaissance** and **SQL Injection (SQLi)** against two deliberately vulnerable, legal practice environments:

- **Mediroza** — a fictional hospital web application (Patient Portal) used strictly for training purposes.
- **OWASP Juice Shop** — an intentionally insecure web application maintained by OWASP for security education.

> ⚠️ **Disclaimer:** All testing in this repository was performed on authorized, intentionally vulnerable training applications. No real systems, real patient data, or production environments were accessed. This content is for educational purposes only — do not test systems you do not own or have explicit written permission to test.

---

## 🎯 Objective
- Practice the early stages of the penetration testing methodology: **reconnaissance** and **enumeration**.
- Understand how improperly sanitized user input leads to **authentication bypass** via SQL Injection.
- Reinforce secure coding takeaways that apply directly to a SOC Analyst / Blue Team perspective.

---

## 🛠️ Tools Used
| Tool | Purpose |
|---|---|
| Browser Dev Tools | Inspecting form fields and page structure |
| Manual SQL Injection | Testing login form input handling |
| OWASP Juice Shop | Practicing broader web vulnerability categories |

---

## 🔍 Methodology

### 1. Reconnaissance
- Identified the target application structure: `Home`, `About`, `Doctors`, `Contact`, and `Patient Portal` pages.
- Located the authentication entry point: the **Patient Portal** login form (Username / Password).
- Observed the form had no visible client-side input restrictions.

### 2. Vulnerability Testing (SQL Injection)
- Tested the login form for classic SQL Injection authentication bypass patterns (e.g., logically-true conditions in the input).
- Confirmed the backend was concatenating user input directly into a SQL query without parameterization or input sanitization, allowing the login check to be bypassed.

### 3. OWASP Juice Shop
- Used Juice Shop's challenge-based format to practice additional web vulnerability classes (injection, broken access control, etc.) in a safe, gamified environment.

---

## ✅ Key Takeaways (Blue Team Lens)
- **Recon comes first** — both attackers and defenders start by mapping the application's attack surface.
- **Never trust user input** — always use parameterized queries / prepared statements, never string concatenation in SQL.
- **Defense in depth** — input validation, least-privilege database accounts, and WAF rules all reduce impact even if one layer fails.
- **Healthcare context matters** — a single SQLi flaw in a patient portal could expose sensitive medical records, raising both security and compliance stakes.

---

## 🧰 Remediation Recommendations
1. Use parameterized queries / an ORM instead of raw string concatenation.
2. Apply strict server-side input validation and sanitization.
3. Enforce least-privilege database accounts for the web application.
4. Implement account lockout / rate limiting on login attempts.
5. Run regular automated security scans (e.g., OWASP ZAP) in the CI/CD pipeline.

---

## 📂 Repository Structure
![](Screenshot_20261126_201543_LinkedIn.Jpg)
.
├── README.md          # This file
├── screenshots/        # Evidence captured during the lab
└── notes.md            # Personal lab notes and reflections
```

---

## 🏷️ Tags
`#NetworkWalks` `#EthicalHacking` `#CyberSecurity` `#SQLInjection` `#OWASP` `#JuiceShop` `#SOCAnalyst` `#WebSecurity`

---

*Part of my ongoing, self-paced journey toward a SOC Analyst role.*

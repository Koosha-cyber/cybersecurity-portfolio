# Findings — Lab-Only

This file contains documentation of vulnerabilities identified and fixed during practice labs  
(PortSwigger Academy, TryHackMe, OWASP Juice Shop, etc.).

⚠️ Reminder: All tests are done in legal labs only. Never on real systems.

---

## Example 1: Reflected XSS
- **Platform/Lab:** PortSwigger Academy (Reflected XSS)
- **Context:** Search input field
- **Payload (Lab Only):** `<script>alert(1)</script>`
- **Evidence:** ./screenshots/xss.png
- **Impact:** Client-side script execution (possible session hijacking in real apps)
- **Risk:** Medium (~6.x CVSS)
- **Remediation:** Input validation, output encoding, enable Content Security Policy

---

## Example 2: SQL Injection
- **Platform/Lab:** TryHackMe OWASP Top 10
- **Context:** Login form
- **Payload (Lab Only):** `' OR '1'='1`
- **Evidence:** ./screenshots/sqli.png
- **Impact:** Unauthorized access to database
- **Risk:** High (~8.x CVSS)
- **Remediation:** Use prepared statements / parameterized queries, error handling

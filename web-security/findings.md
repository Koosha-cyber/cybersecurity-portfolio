# Findings — Lab-Only

This file contains documentation of vulnerabilities identified and fixed during practice labs  
(PortSwigger Academy, TryHackMe, OWASP Juice Shop, etc.).

⚠️ Reminder: All tests are done in legal labs only. Never on real systems.

---

## Example 1: Stored XSS — Blog Comments (PortSwigger Lab)

- **Platform/Lab:** PortSwigger Web Security Academy — *Stored XSS into HTML context with nothing encoded*  
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/stored  
- **Context:** Blog comment form (user input stored in DB and reflected into HTML body without encoding)  

- **Payload (Lab Only):**
  ```html
  <script>alert('XSS')</script>
- **Evidence:** ./screenshots/XSS_2.1.png, XSS_2.2.png, XSS_2.3.png
- **Impact:** Any visitor executes attacker-controlled JavaScript → risk of session hijacking, phishing, defacement.
- **Risk:** High
- **Remediation:**
- - Encode user input before injecting into HTML  
  - Sanitize input server-side  
  - Apply CSP
 
  - ---

  ---

## Example 2: Reflected XSS — Search Field

Platform/Lab: PortSwigger Web Security Academy – Reflected XSS into HTML context with nothing encoded

Lab URL (description): https://portswigger.net/web-security/cross-site-scripting/reflected

Context: Search input field (user input reflected directly into HTML page)

Payload (Lab Only):
<script>alert('XSS')</script>
Evidence: ./screenshots/XSS_2.1.png, ./screenshots/XSS_2.2.png

Impact: Attacker-controlled script executes in the victim’s browser → risk of session hijacking, credential theft, phishing.

Risk: Medium-High (~6.x CVSS)

Remediation:

Encode user input before injecting into HTML

Sanitize input server-side

Apply Content Security Policy (CSP)

  


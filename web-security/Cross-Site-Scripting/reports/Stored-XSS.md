# Report – Stored XSS (Blog Comments)

**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** Stored XSS into HTML context with nothing encoded  
**Date:** 2025-08-28  

---

## 📌 Summary
The blog comment form stores unsanitized user input in the database and reflects it into the HTML body without proper encoding.  
As a result, any visitor to the blog page will execute attacker-controlled JavaScript code.  

---

## 🔬 Technical Details
- **Context:** Blog comment form (input stored in DB and rendered into HTML)  
- **Payload (Lab Only):**
```html
<script>alert('XSS')</script>

  Evidence:
    - ../screenshots/XSS_2.1.png
    - ../screenshots/XSS_2.2.png
    - ../screenshots/XSS_2.3.png

⚠️ Impact

Execution of attacker-controlled JavaScript

Risk of session hijacking, phishing, or defacement

Risk: High (CVSS ~6.1–6.5)

🎯 Remediation

Encode user input before injecting into HTML

Sanitize input server-side

Apply Content Security Policy (CSP)

References:
  - "OWASP XSS Prevention Cheat Sheet: https://owasp.org/www-community/xss-prevention"
  - "PortSwigger XSS Labs: https://portswigger.net/web-security/cross-site-scripting"

Tags:
  - web-security
  - stored-xss
  - owasp-top10
  - portswigger


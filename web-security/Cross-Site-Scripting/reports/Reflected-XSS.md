# Report – Reflected XSS (Search Field)

**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** Reflected XSS into HTML context with nothing encoded  
**Date:** 2025-08-29  

---

## 📝 Summary
The search functionality reflects unsanitized user input directly into the HTML response without proper encoding.  
As a result, attacker-controlled JavaScript can execute in the victim’s browser.

---

## 🔍 Technical Details
**Context:** Search field (input reflected into HTML response)  

**Payload (Lab Only):**
```html
<script>alert</script>

Evidence:
../screenshots/Reflected-XSS-1.png
../screenshots/Reflected-XSS-2.png

⚠️ Impact

Execution of arbitrary JavaScript in the victim’s browser

Risk of session hijacking, phishing, or defacement

Sensitive data exposure (cookies, session tokens)

🎯 Risk

Severity: High

🛠️ Remediation

Encode user input before reflecting into HTML

Sanitize input server-side

Apply Content Security Policy (CSP)

📚 References

OWASP XSS Prevention Cheat Sheet

PortSwigger Academy – XSS Labs

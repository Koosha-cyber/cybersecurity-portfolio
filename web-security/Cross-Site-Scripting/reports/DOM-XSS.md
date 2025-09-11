# Report – DOM XSS (document.write sink with location.search source)

**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** DOM XSS in `document.write` sink using source `location.search`  
**Date:** 2025-08-29  

---

## 📝 Summary
The application is vulnerable to **DOM-based Cross-Site Scripting (XSS)** because untrusted data from `location.search` is directly written into the DOM using `document.write` without sanitization or encoding.  
As a result, an attacker can execute arbitrary JavaScript code in the victim’s browser.

---

## 🔬 Technical Details
- **Source:** `location.search` (user-controllable URL parameter)  
- **Sink:** `document.write` (dangerous DOM API that writes directly into HTML)  

**Payload (Lab Only):**
```html
<script>alert(1)</script>

When encoded with %27 ('), the payload failed due to broken string context.

When encoded with %22 ("), the payload executed successfully, confirming the DOM XSS vulnerability.

📸 Evidence
../screenshots/DOM-XSS-1.png
../screenshots/DOM-XSS-2.png
../screenshots/DOM-XSS-3.png

🎯 Impact

Arbitrary JavaScript execution in the victim’s browser.

Can lead to session hijacking, phishing, credential theft, defacement, or redirection to malicious sites.

Risk: High 🔴

🛠️ Remediation

Avoid using dangerous sinks such as document.write.

Use safe DOM APIs like textContent or innerText instead of writing raw HTML.

Implement context-aware output encoding.

Apply a strong Content Security Policy (CSP) to reduce impact.

📚 References

PortSwigger DOM XSS Guide

OWASP XSS Prevention Cheat Sheet

Tags: web-security, dom-xss, owasp-top10, portswigger

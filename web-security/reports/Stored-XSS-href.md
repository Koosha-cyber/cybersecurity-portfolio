**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** Stored XSS into anchor `href` attribute with double quotes HTML-encoded  
**Date:** 2025-09-03  

---

## Summary  
The application reflects unsanitized user input inside an anchor tag (`<a href>`).  
Although double quotes are HTML-encoded, attackers can still inject `javascript:` schemes, leading to execution of arbitrary code when the victim clicks the link.  

---

## Technical Details  
**Context:** User input stored in DB → rendered into `href` attribute of an `<a>` tag.  
**Payload (Lab Only):**
```html
javascript:alert(1)
Evidence:

screenshots/Stored-XSS-attribute-href-1.png

screenshots/Stored-XSS-attribute-href-2.png

Impact
Arbitrary JavaScript execution

Redirection to attacker-controlled pages

Session hijacking, credential theft, phishing

Risk Rating: High

Remediation
Encode user input before inserting into attribute values

Block dangerous protocols (javascript: / data:)

Use allowlist validation for safe URL schemes

Apply CSP to mitigate possible exploit

References
OWASP XSS Prevention Cheat Sheet

PortSwigger XSS Labs

Tags
web-security, stored-xss, attribute-injection, href, portswigger, owasp-top10

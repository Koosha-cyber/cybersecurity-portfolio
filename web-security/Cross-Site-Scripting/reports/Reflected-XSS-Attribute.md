**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** Reflected XSS into attribute with angle brackets HTML-encoded  
**Date:** 2025-08-30  

---

## Summary  
The application reflects user-supplied input inside an HTML attribute value.  
Although angle brackets (`< >`) are HTML-encoded, injection is possible using attributes such as `autofocus` or `onfocus`, which allow arbitrary JavaScript execution.  

---

## Technical Details  
**Context:** Input reflected inside an attribute value (with HTML encoding).  
**Payload (Lab Only):**
```html
" autofocus onfocus=alert(1) x
Evidence:

screenshots/Reflected-XSS-attribute with angle brackets HTML-1.png

screenshots/Reflected-XSS-attribute with angle brackets HTML-2.png

Impact
Arbitrary JavaScript execution

Risk of phishing, credential theft, or session hijacking

Risk Rating: High

Remediation
Ensure strict HTML attribute encoding (" and ')

Sanitize user input against malicious attribute injections

Use CSP to reduce XSS impact

References
OWASP XSS Prevention Cheat Sheet

PortSwigger Attribute-based XSS

Tags
web-security, reflected-xss, attribute-injection, portswigger, owasp-top10

**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** DOM XSS in jQuery selector sink using a hashchange event  
**Date:** 2025-09-01  

---

## Summary
The application uses jQuery’s `$()` selector with input from `location.hash` inside a `hashchange` event.  
This allows an attacker to inject arbitrary JavaScript payloads, leading to DOM-based XSS.  

---

## Technical Details

- **Context:** `location.hash` is passed directly to jQuery’s selector (`$()`).  
- **Payload (Lab Only):**
```html
#<img src=x onerror=print()>
Evidence:

./screenshots/DOM-XSS-jQuery-hashchange-1.png

Impact
Arbitrary JavaScript execution in victim’s browser.

Risk of session hijacking, phishing, credential theft.

Exploitability is high since the sink is directly reachable.

Risk: High (CVSS ~7.5)

Remediation
Do not pass untrusted input (location.hash) directly into jQuery selectors.

Use strict input validation/encoding.

Replace innerHTML/unsafe selectors with safer alternatives (textContent, setAttribute).

Apply Content Security Policy (CSP).

References
OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

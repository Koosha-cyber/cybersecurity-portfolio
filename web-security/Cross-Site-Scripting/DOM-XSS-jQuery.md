**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** DOM XSS in jQuery anchor `href` sink using source `location.search`  
**Date:** 2025-08-30  

---

## Summary
The application uses jQuery to update an anchor (`<a>`) element’s `href` attribute with user input taken from `location.search`. Because this input is not sanitized, an attacker can inject a malicious `javascript:` URI, leading to DOM-based XSS.

---

## Technical Details

- **Source:** `location.search` (`returnPath` parameter)  
- **Sink:** jQuery assignment to `<a href="...">`  
- **Vulnerable pattern (conceptual):**
  ```js
  $('a#backLink').attr('href', location.search.split('returnPath=')[1]);
Steps to Reproduce (Lab Only)
Navigate to the lab’s feedback page.

Inject payload in query parameter:

javascript
Copy code
?returnPath=javascript:alert(document.domain)
Hover or click the link created on the page.

The malicious JavaScript is executed in the victim’s browser.

Evidence:

./screenshots/DOM-XSS- in jQuery-1.png

./screenshots/DOM-XSS- in jQuery-2.png

Impact
Arbitrary JavaScript execution in victim browser.

Risk of session hijacking, credential theft, phishing, redirection to malicious sites.

Risk: High

Root Cause
Direct assignment of unsanitized user input into sensitive attributes (href).

No validation of allowed URL schemes (e.g., https://, mailto:).

Remediation
Use strict input validation and allowlist only safe URL schemes.

Avoid setting href attributes directly with user input.

Consider using safe navigation patterns (window.location with validation).

Enforce Content Security Policy (CSP).

Validation After Fix
Repeat payload injection with ?returnPath=javascript:alert(1) → link should not execute JavaScript.

Ensure only legitimate, validated URLs are accepted.

References
OWASP DOM XSS Prevention Cheat Sheet

PortSwigger Web Security Academy — DOM XSS Labs

Appendix — Payloads (Lab Only)
?returnPath=javascript:alert(1)

?returnPath=javascript:alert(document.cookie)

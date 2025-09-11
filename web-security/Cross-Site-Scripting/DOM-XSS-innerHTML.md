**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** DOM XSS in `innerHTML` sink using source `location.search`  
**Date:** 2025-08-30

---

## Summary
The application reads user-controlled data from `location.search` and writes it into a page `<div>` using `element.innerHTML`. Because the value is not validated/sanitized or encoded, an attacker can inject HTML/JavaScript that executes in the victim’s browser.

---

## Technical Details

- **Source:** `location.search` (query string parameter `?search=...`)
- **Sink:** `element.innerHTML` (content of a `<div>` on the results page)
- **Vulnerable pattern (conceptual):**
  ```js
  const q = new URLSearchParams(location.search).get('search');
  document.querySelector('#results').innerHTML = `0 search results for "${q}"`;
  Steps to Reproduce (Lab Only)

Open the lab page (search view).

Append the following payload to the URL query string:

Raw (HTML):

?search=<img src=x onerror=alert(1)>


URL-encoded:

?search=%3Cimg%20src%3Dx%20onerror%3Dalert(1)%3E


Load the page. The payload is rendered via innerHTML and triggers alert(1).

Evidence:

./screenshots/DOM-XSS-innerHTML-1.png

./screenshots/DOM-XSS-innerHTML-2.png

Impact

Execution of arbitrary JavaScript in the user’s session.

Potential session hijacking, credential theft, phishing, UI redress/defacement.

Abuse of authenticated context and sensitive actions.

Risk: High

Root Cause

Direct use of innerHTML with user-controlled data.

No input validation/sanitization; no output encoding for HTML context.

Missing defense-in-depth (e.g., restrictive CSP).

Remediation

Replace innerHTML with textContent/innerText where possible:

el.textContent = `0 search results for "${q}"`;


If HTML is required, sanitize with a vetted library (e.g., DOMPurify):

el.innerHTML = DOMPurify.sanitize(userHtml);


Validate and canonicalize input; encode based on sink context.

Deploy a restrictive Content Security Policy (CSP) to limit script execution.

Add automated tests for DOM XSS sinks (innerHTML, outerHTML, insertAdjacentHTML, document.write, jQuery.html, etc.).

Validation After Fix

Repeat steps with the same payload; HTML should be treated as plain text or removed by sanitizer.

No script execution and no browser alert should occur.

References

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger Web Security Academy — DOM-based XSS

Appendix — Payloads (Lab Only)

<img src=x onerror=alert(1)>

%3Cimg%20src%3Dx%20onerror%3Dalert(1)%3E

<svg onload=alert(1)>

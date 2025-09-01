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
 📄 [Detailed Report](./reports/Stored-XSS.md)
References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

Tags:

web-security

stored-xss

owasp-top10

portswigger

  - ---

  ---

## Example 2: Reflected XSS — Search Field

- **Platform/Lab:** PortSwigger Web Security Academy – Reflected XSS into HTML context with nothing encoded
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/reflected
- **Context:** Search input field (user input reflected directly into HTML page)
- 
- **Payload (Lab Only):**
  ```html
  <script>alert('XSS')</script>
- **Evidence:** ./screenshots/XSS_2.1.png, ./screenshots/XSS_2.2.png
- **Impact:** Attacker-controlled script executes in the victim’s browser → risk of session hijacking, credential theft, phishing.
- **Risk:** Medium-High (~6.x CVSS)

- **Remediation:**

- - Encode user input before injecting into HTML

  - Sanitize input server-side

  - Apply Content Security Policy (CSP)

References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

Tags:

web-security

reflected-xss

owasp-top10

portswigger

➡️ Detailed Report
  - ---

  ---
## Example 3: DOM XSS — document.write sink (PortSwigger Lab)

- **Platform/Lab:** PortSwigger Web Security Academy — DOM XSS in document.write sink using source location.search  
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/dom-based  
- **Context:** `location.search` (user input) written unsafely into HTML via `document.write`

- **Payload (Lab Only):**
  ```html
  <script>alert(1)</script>
- **Evidence:** ./screenshots/DOM-XSS-1.png, ./screenshots/DOM-XSS-2.png, ./screenshots/DOM-XSS-3.png
- **Impact:** Arbitrary JavaScript execution → risk of session hijacking, phishing, defacement
- **Risk:** High
- **Remediation:**

Use textContent or innerText instead of document.write

Validate and sanitize user input

Apply CSP

References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

Tags:

web-security

dom-xss

owasp-top10

portswigger

➡️ Detailed Report
  - ---

  ---
## Example 4: DOM XSS — innerHTML sink (PortSwigger Lab)

- **Platform/Lab:** PortSwigger Web Security Academy – *DOM XSS in `innerHTML` sink using source `location.search`*
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/dom-based
- **Context:** `location.search` (user-controlled query string) is written unsafely into a page `<div>` via `element.innerHTML`.

- **Payload (Lab Only):**
  ```html
  <img src=x onerror=alert(1)>
- **Evidence:** ./screenshots/DOM-XSS-innerHTML-1.png, ./screenshots/DOM-XSS-innerHTML-2.png
- **Impact:** Arbitrary JavaScript execution in victim’s browser → risk of session hijacking, credential theft, phishing, defacement.
- **Risk:** High
- **Remediation:**
Avoid innerHTML for inserting user input; use textContent/innerText or safe DOM APIs.

If HTML is truly required, sanitize with a trusted library (e.g., DOMPurify) before insertion.

Validate and encode user-controlled data appropriately.

Apply Content Security Policy (CSP) to reduce XSS impact.

References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

---

## Example 5: DOM XSS — jQuery anchor `href` sink (PortSwigger Lab)

- **Platform/Lab:** PortSwigger Web Security Academy – *DOM XSS in jQuery anchor `href` attribute sink using source `location.search`*
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/dom-based
- **Context:** `location.search` value is inserted into an anchor `<a>` tag `href` attribute by jQuery without sanitization.

- **Payload (Lab Only):**
  ```html
  ?returnPath=javascript:alert(document.domain)

- **Evidence:** ./screenshots/DOM-XSS-in jQuery-1.png, ./screenshots/DOM-XSS-in jQuery-2.png

- **Impact:** Attacker can inject malicious JavaScript via crafted URL → arbitrary code execution, phishing, credential theft.

- **Risk:** High

- **Remediation:**
Do not assign user input directly to href attributes.

Validate and sanitize all query string parameters.

Explicitly block dangerous protocols (javascript:, data:, etc.).

Apply CSP (Content Security Policy) to mitigate XSS exploitation.

References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

Tags: web-security, dom-xss, jquery, owasp-top10, portswigger

➡️ Detailed Report
  - ---

  ---
### Example 6: DOM XSS — jQuery selector sink using hashchange event (PortSwigger Lab)

- **Platform/Lab:** PortSwigger Web Security Academy – *DOM XSS in jQuery selector sink using a hashchange event*  
- **Lab URL (description):** https://portswigger.net/web-security/cross-site-scripting/dom-based  
- **Context:** `location.hash` (user-controlled input) passed directly to jQuery’s `$()` selector inside a `hashchange` event.  

- **Payload (Lab Only):**
  ```html
  #<img src=x onerror=print()>
- **Evidence:** ./screenshots/DOM-XSS-jQuery-hashchange-1.png, ./screenshots/DOM-XSS-jQuery-hashchange-2.png
- **Impact:** Attacker-controlled code execution in victim’s browser → risk of arbitrary JavaScript execution, phishing, credential theft.

- **Risk:** High

- **Remediation:**

Avoid passing location.hash directly to jQuery selectors.

Sanitize and validate hash values before use.

Apply CSP (Content Security Policy).

References:

OWASP DOM XSS Prevention Cheat Sheet

PortSwigger DOM XSS Labs

📄 Detailed Report

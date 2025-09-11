# DOM XSS — document.write using location.search

**Context:** `document.write(location.search)` executes untrusted input  
**Payload (lab-only):** `?q=<script>alert(1)</script>`  
**Evidence:** [1](../../Cross-Site-Scripting/screenshots/DOM-XSS-1.png) [2](../../Cross-Site-Scripting/screenshots/DOM-XSS-2.png) [3](../../Cross-Site-Scripting/screenshots/DOM-XSS-3.png)  
**Full report:** ../../Cross-Site-Scripting/reports/DOM-XSS.md  
**Remediation:** Avoid sinks like `document.write`; use safe DOM APIs

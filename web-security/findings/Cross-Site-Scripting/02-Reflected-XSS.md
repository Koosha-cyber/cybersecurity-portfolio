# Reflected XSS — HTML context (nothing encoded)

**Context:** User input reflected in HTML without encoding  
**Payload (lab-only):** `<script>alert('XSS')</script>`  
**Evidence:** See screenshots [1](../../Cross-Site-Scripting/screenshots/Reflected-XSS-1.png) [2](../../Cross-Site-Scripting/screenshots/Reflected-XSS-2.png)  
**Full report:** ../../Cross-Site-Scripting/reports/Reflected-XSS.md  
**Remediation:** Output encoding, input validation, consider CSP

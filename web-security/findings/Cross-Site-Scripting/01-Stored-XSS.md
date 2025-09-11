# Stored XSS — HTML context (nothing encoded)

**Context:** Comment stored in DB and rendered into HTML unencoded  
**Payload (lab-only):** `<script>alert('XSS')</script>`  
**Evidence:** [1](../../Cross-Site-Scripting/screenshots/XSS-2.1.png) [2](../../Cross-Site-Scripting/screenshots/XSS-2.2.png) [3](../../Cross-Site-Scripting/screenshots/XSS-2.3.png)    
**Full report:** ../../Cross-Site-Scripting/reports/Stored-XSS.md  
**Remediation:** Encode before render; server-side sanitization; CSP

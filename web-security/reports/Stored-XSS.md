# Report – Stored XSS (Blog Comments)

**Scope:** PortSwigger Web Security Academy (training lab only)  
**Lab:** Stored XSS into HTML context with nothing encoded  
**Date:** 2025-08-28  

---

## Summary
The blog comment form stores unsanitized user input in the database and reflects it into the HTML body without proper encoding.  
As a result, any visitor to the blog page will execute attacker-controlled JavaScript code.

---

## Technical Details
**Context:** Blog comment form (user input stored in DB and rendered into HTML)  
**Payload (Lab Only):**
```html
<script>alert('XSS')</script>

# ================================
# Vulnerability Report
# ================================

id: stored-xss-blog-comments
title: "Stored XSS in Blog Comments"
platform: "PortSwigger Web Security Academy (training lab only)"
lab_url: "https://portswigger.net/web-security/cross-site-scripting/stored"
date: 2025-08-28
author: Koosha M. Behbahani

Summary: |
  The blog comment form fails to sanitize user input before storing it in the database. 
  This data is later rendered in the HTML body without encoding, allowing malicious JavaScript execution.

Technical_details:
  context: "Blog comment form (input stored in DB and reflected in HTML)"
  payload: |
    <script>alert('XSS')</script>
  Evidence:
    - ../screenshots/XSS_2.1.png
    - ../screenshots/XSS_2.2.png
    - ../screenshots/XSS_2.3.png

Impact: |
  Any visitor loading the blog page executes attacker-controlled JavaScript.
  This could lead to:
  - Session hijacking
  - Phishing attacks
  - Website defacement

Risk: High (CVSS ~6.1–6.5)

Remediation: |
  - Encode user input before rendering in HTML
  - Sanitize and validate input on server-side
  - Apply Content Security Policy (CSP)

References:
  - "OWASP XSS Prevention Cheat Sheet: https://owasp.org/www-community/xss-prevention"
  - "PortSwigger XSS Labs: https://portswigger.net/web-security/cross-site-scripting"

Tags:
  - web-security
  - stored-xss
  - owasp-top10
  - portswigger


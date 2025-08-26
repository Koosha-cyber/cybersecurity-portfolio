# Final Report — Web Vulnerability Assessment (Lab-Only)

> **Scope:** Legal training platforms only (TryHackMe, PortSwigger Academy, OWASP Juice Shop).  
> **Note:** This report is for learning and portfolio purposes; no real systems were tested.

## 1) Executive Summary
- Objective: Practice OWASP Top 10 in a safe environment and document findings.
- Outcome: Identified and explained common web vulnerabilities and mitigations.
- Deliverables: Findings (Markdown), screenshots, and this final report.

## 2) Methodology
- Approach: Recon → Test → Confirm → Risk rating → Remediation → Report
- Tools (optional): Browser, PortSwigger Academy/THM built-in tools, Burp/ZAP (when relevant)

## 3) Findings (Overview)
List your top 3–5 findings with one-line summaries. Link to details in `findings.md`.

- Reflected XSS — input not encoded → client-side script execution → see `findings.md#reflected-xss-example`
- SQL Injection — unsafely concatenated queries → DB access → see `findings.md#example-2-sql-injection`
- Security Headers — missing CSP / X-Frame-Options → clickjacking/inline scripts

## 4) Detailed Evidence
- Screenshots stored under: `./screenshots/`
- Lab references/IDs: (add URLs/titles of the labs you solved)

## 5) Risk & Impact
- Use a simple scale: High / Medium / Low (or approximate CVSS if you prefer)
- Explain business impact in one sentence per finding.

## 6) Remediation Recommendations
- Input validation & output encoding (server-side)
- Parameterized queries / prepared statements (SQL)
- Security headers: `Content-Security-Policy`, `X-Frame-Options`, `X-Content-Type-Options`, `Referrer-Policy`
- Session security: `HttpOnly`, `Secure`, `SameSite`

## 7) Lessons Learned
- What I practiced and what I would do differently next time.

## 8) Appendix
- Links to labs, references (OWASP Cheat Sheets), extra notes.

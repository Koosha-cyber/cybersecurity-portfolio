# Cross-Site Scripting (XSS) Labs – Apprentice Level

This folder contains my reports and evidence for the **9 Apprentice-level XSS labs** from PortSwigger Web Security Academy.  
All work documented here is performed **only in legal lab environments** (PortSwigger Academy, OWASP Juice Shop, TryHackMe).

---

## 📂 Structure
- `reports/` → Detailed markdown reports for each lab  
- `screenshots/` → Screenshots captured during exploitation and verification  

---

## ✅ Completed Labs (Apprentice Level)

| # | Lab Title | Report | Screenshots |
|---|-----------|--------|-------------|
| 1 | Reflected XSS into HTML context with nothing encoded | [Report](reports/Reflected-XSS.md) | [1](screenshots/Reflected-XSS-1.png) [2](screenshots/Reflected-XSS-2.png) |
| 2 | Stored XSS into HTML context with nothing encoded | [Report](reports/Stored-XSS.md) | [1](screenshots/Stored-XSS-1.png) [2](screenshots/Stored-XSS-2.png) |
| 3 | DOM XSS in document.write sink using location.search | [Report](reports/DOM-XSS.md) | [1](screenshots/DOM-XSS-1.png) [2](screenshots/DOM-XSS-2.png) [3](screenshots/DOM-XSS-3.png) |
| 4 | DOM XSS in jQuery selector sink using a hashchange event | [Report](reports/DOM-XSS-jQuery-hashchange.md) | [1](screenshots/DOM-XSS-jQuery-hashchange-1.png) [2](screenshots/DOM-XSS-jQuery-hashchange-2.png) |
| 5 | DOM XSS in jQuery anchor href sink | [Report](reports/DOM-XSS-jQuery.md) |  [1](screenshots/DOM-XSS-in jQuery-1.png) [2](screenshots/DOM-XSS-in jQuery-2.png) |
| 6 | DOM XSS in innerHTML sink | [Report](reports/DOM-XSS-innerHTML.md) | — |
| 7 | Reflected XSS into attribute with angle brackets HTML-encoded | [Report](reports/Reflected-XSS-Attribute.md) | — |
| 8 | Reflected XSS into JavaScript string with angle brackets HTML-encoded | [Report](reports/Reflected-XSS-JS-String.md) | — |
| 9 | Stored XSS into anchor href attribute with double quotes HTML-encoded | [Report](reports/Stored-XSS-href.md) | — |

---

## 🔎 Methodology
Each lab write-up includes:
1. Context (where the vulnerability occurs)  
2. Payloads used (lab-only, safe)  
3. Evidence (screenshots)  
4. Impact (real-world risk)  
5. Remediation steps  

---

📌 *This folder is part of my cybersecurity portfolio: documenting practical web security labs and remediation strategies.*

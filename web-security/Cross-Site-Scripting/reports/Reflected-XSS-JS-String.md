This lab demonstrates a **Reflected Cross-Site Scripting (XSS)** vulnerability where user input is reflected into a **JavaScript string context**.  
Although `<` and `>` are encoded (blocking `<script>` injection), single and double quotes are not encoded, allowing an attacker to break out of the string and execute arbitrary JavaScript.

## ⚡ Evidence
- Injected payload:  
  ```javascript
  ';alert(1);// 
Execution: The injected payload broke out of the JavaScript string and executed an alert(1).

Screenshots: Reflected-XSS-JS-String-1.png, Reflected-XSS-JS-String-2.png

🎯 Impact
Arbitrary JavaScript execution in the victim’s browser

Potential consequences:

Session hijacking

Theft of credentials

Redirection to malicious sites

Defacement / phishing

Risk: High

🛠️ Remediation
Always escape user input before placing it in JavaScript strings.

Use JSON encoding when embedding untrusted data in JavaScript.

Implement Content Security Policy (CSP) to restrict script execution.

Sanitize and validate user input server-side.

📚 References
OWASP XSS Prevention Cheat Sheet

PortSwigger Labs – Reflected XSS in JS context


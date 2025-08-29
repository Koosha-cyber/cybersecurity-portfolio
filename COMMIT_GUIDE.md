# 📝 Commit Message Guide — cybersecurity-portfolio

This guide ensures all commit messages in this repository are **clear, consistent, and professional**.

---

## 1) Commit Message Format (mandatory)

**Examples:**
- `Add findings.md: Stored XSS (PortSwigger Lab)`
- `Add report: Stored XSS (Blog Comments)`
- `Add evidence: Stored XSS (screenshots)`
- `Update README.md: add Stored XSS reference`
- `Fix findings.md: screenshot path`
- `Remove .keep from screenshots/`

**Standard Actions:**
- **Add** → for new files, reports, findings, evidence  
- **Update** → for improvements or edits  
- **Fix** → for correcting mistakes (paths, typos, wrong links)  
- **Remove** → for deleting unnecessary files  
- **Refactor** → for reorganizing structure without content change  

---

## 2) Common Patterns for This Repository

### Findings (`/web-security/findings.md`)
- Add new finding:  
  `Add finding: <Vuln> (<Platform/Lab>)`  
  Example: `Add finding: Reflected XSS (PortSwigger Lab)`
- Update existing finding:  
  `Update finding: <Vuln> (<Platform/Lab>)`

### Reports (`/web-security/reports/*.md`)
- Add new detailed report:  
  `Add report: <Vuln> (<Context/Scenario>)`  
  Example: `Add report: Reflected XSS (Search field)`
- Update existing report:  
  `Update report: <Vuln> (<Context/Scenario>)`

### Evidence / Screenshots (`/web-security/screenshots/`)
- Add screenshot evidence:  
  `Add evidence: <Vuln> (<Platform/Lab>)`  
- Update/replace evidence:  
  `Update evidence: <Vuln>`  
- Remove outdated/duplicate evidence:  
  `Remove evidence: <Vuln> (old/duplicate)`

### README files
- Add new reference to finding/report:  
  `Update README.md: add <Vuln> reference`  
- Improve structure or sections:  
  `Update README.md: improve <section>`  

---

## 3) 10-Second Checklist Before Commit
- [ ] Action word (Add / Update / Fix / Remove / Refactor) included  
- [ ] Vulnerability/subject name mentioned (e.g., Stored XSS)  
- [ ] File or section is specified (findings.md, reports/, screenshots/, README.md)  
- [ ] Description is short, clear, and professional  

---

## 4) Anti-Patterns (Avoid These)
❌ `update`  
❌ `fix stuff`  
❌ `changes`  
❌ `final`  
❌ long or vague commit messages  

(If extra explanation is needed → use the **Extended Description** box, not the title line.)

---

## 5) Golden Rule
**Every commit message must explain clearly what changed, where it changed, and why.**  
This makes your project history **professional, easy to review, and recruiter-friendly.**

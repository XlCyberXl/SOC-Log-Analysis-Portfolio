# Da'Shayne's Portfolio of Cybersecurity Projects

## Overview
This repository contains hands-on SOC and Incident Response log analysis investigations focused on identifying, validating, and documenting real-world attack techniques using web server logs and SIEM data.

Each project follows a structured SOC workflow:
- Alert or detection review
- Evidence-based log analysis
- Determination of attack success or failure
- Clear, defensible conclusions
- Security recommendations

All investigations are documented step-by-step, with each step mapped to supporting evidence and screenshots.

---

## Analyst Background
I currently work in technical support and am transitioning into a SOC / Information Security role.

I have hands-on experience analyzing:
- Web server access logs
- Authentication and login activity
- SIEM alerts related to web exploitation and abuse patterns

My investigation style emphasizes:
- Strict step-by-step analysis
- Evidence-driven conclusions
- Clear differentiation between attempted and successful exploitation

---

## Investigation Projects

### [1. Command Injection – High SIEM Alert](./01-Command-Injection/)

**Type:** Web Application Attack Investigation  
**Logs Analyzed:** Apache Access Logs  
**Skills Demonstrated:** Log Analysis, Command Injection Investigation
### [2. IDOR (Insecure Direct Object Reference) Log Analysis](./02-IDOR-Log-Analysis/)
Type: Web Application Authorization Vulnerability Analysis  
Logs Analyzed: Web Server Access Logs  
Skills Demonstrated: Access Control Analysis, Authorization Bypass Detection  
### [3. LFI / RFI – SIEM Alert Investigation](./03-LFI-RFI-SIEM-Alert/)
**Type:** SIEM Alert Triage & Validation  
**Data Reviewed:** SIEM Alerts, Web Traffic  
**Skills Demonstrated:** Alert Analysis, False Positive Validation  
 
### [4. Open Redirect Log Analysis](./04-Open-Redirect-Log-Analysis/)
**Type:** Web Application Vulnerability Analysis  
**Logs Analyzed:** Web Server Access Logs  
**Skills Demonstrated:** Redirect Abuse Detection, Log Correlation
05. Directory Traversal Log Analysis  
06. Brute Force Attack Log Analysis  
07. XML External Entity (XXE) Log Analysis  
### [8. Cross-Site Scripting (XSS) Log Analysis](./08-XSS-Log-Analysis/)

**Type:** Web Application Attack Investigation  
**Logs Analyzed:** Apache Access Logs  
**Skills Demonstrated:** Log Analysis, XSS Detection, Incident Response 
09. SQL Injection (SQLi) Log Analysis  

---

## How to Use This Repository
Each project is contained in its own folder and includes:
- A detailed README documenting the investigation
- Step-by-step analysis mapped to screenshots
- Evidence supporting conclusions
- Mitigation and security recommendations

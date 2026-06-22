# Da'Shayne's Cybersecurity Portfolio

## Overview
This repository contains hands-on SOC and Incident Response investigations 
focused on identifying, validating, and documenting real-world attack techniques 
using web server logs, SIEM data, and AI-powered automation.

Each project follows a structured SOC workflow:
- Alert or detection review
- Evidence-based log analysis
- Determination of attack success or failure
- Clear, defensible conclusions
- Security recommendations

All investigations are documented step-by-step, with each step mapped to 
supporting evidence and screenshots.

---

## Analyst Background
I currently work in Security Operations and am actively growing into 
an Information Security analyst role.

Dedicated SOC Analyst Candidate 🛡️

Focused on mastering the art of the investigation. I have built a hands-on 
lab environment to simulate and defend against modern threats.

Core Competencies:

🤖 SOC Automation: Building AI-powered triage tools that integrate with SIEM 
platforms to automate alert analysis and reduce mean time to respond (MTTR).

🛡️ SIEM Triage: Correlating alerts with endpoint telemetry to validate and 
escalate threats.

📊 Log Analysis: Deep-dive inspection of Web Server access logs for malicious 
traffic.

📑 Incident Documentation: Translating complex log data into clear, concise 
incident reports.

---

## Home Labs

### [11. AI-Enhanced SOC Automation: From SIEM Alerts to Intelligent Triage](./11-ai-soc-triage-bot/)
**Type:** SOC Automation & AI Integration  
**Environment:** Windows, Wazuh SIEM, Groq AI (LLaMA 3.3)  
**Skills Demonstrated:** Python Scripting, AI Integration, Prompt Engineering, 
MITRE ATT&CK Mapping, OWASP Classification, SOC Automation

### [10. Wazuh SIEM: Endpoint Monitoring & File Integrity Monitoring (FIM)](./10-wazuh-home-lab/)
**Type:** SIEM Deployment & Endpoint Security  
**Environment:** Ubuntu (Manager), Windows (Agent)  
**Skills Demonstrated:** SIEM Administration, File Integrity Monitoring (FIM), 
XML Configuration, Real-Time Alerting

---

## Investigation Projects

> 💡 **Note on Investigation Data:** The projects featured in this portfolio 
are simulated attack investigations based on lab environments from 
industry-recognized training platforms, **LetsDefend** X **Hack The Box**.

### [9. SQL Injection (SQLi) – SIEM Alert Investigation](./09-SQL-Injection-SIEM-Alert/)
**Type:** SIEM Alert Triage & Validation  
**Data Reviewed:** SIEM Alerts, Apache Access Logs  
**Skills Demonstrated:** Alert Analysis, SQL Injection Detection, Log Correlation

### [8. Cross-Site Scripting (XSS) Log Analysis](./08-XSS-Log-Analysis/)
**Type:** Web Application Attack Investigation  
**Logs Analyzed:** Apache Access Logs  
**Skills Demonstrated:** Log Analysis, XSS Detection, Incident Response

### [7. XML External Entity (XXE) Log Analysis](./07-XML-External-Entity-XXE-Log-Analysis/)
**Type:** Web Application Log Analysis  
**Logs Analyzed:** Web Server & Application Logs  
**Skills Demonstrated:** XML Payload Analysis, Exploit Detection, 
Application Log Review

### [6. Brute Force Attack Log Analysis](./06-brute-force-attack-log-analysis/)
**Type:** Authentication Log Analysis  
**Logs Analyzed:** Authentication & Web Server Access Logs  
**Skills Demonstrated:** Brute Force Detection, Login Pattern Analysis, 
HTTP Response Interpretation

### [5. Directory Traversal Log Analysis](./05-Directory-Traversal-Log-Analysis/)
**Type:** Web Attack Log Analysis  
**Logs Analyzed:** Web Server Access Logs  
**Skills Demonstrated:** Path Traversal Detection, HTTP Log Analysis, 
Exploitation Validation

### [4. Open Redirect Log Analysis](./04-Open-Redirect-Log-Analysis/)
**Type:** Web Application Vulnerability Analysis  
**Logs Analyzed:** Web Server Access Logs  
**Skills Demonstrated:** Redirect Abuse Detection, Log Correlation

### [3. LFI / RFI – SIEM Alert Investigation](./03-LFI-RFI-SIEM-Alert/)
**Type:** SIEM Alert Triage & Validation  
**Data Reviewed:** SIEM Alerts, Web Traffic  
**Skills Demonstrated:** Alert Analysis, False Positive Validation

### [2. IDOR (Insecure Direct Object Reference) Log Analysis](./02-IDOR-Log-Analysis/)
**Type:** Web Application Authorization Vulnerability Analysis  
**Logs Analyzed:** Web Server Access Logs  
**Skills Demonstrated:** Access Control Analysis, Authorization Bypass Detection

### [1. Command Injection – High SIEM Alert](./01-Command-Injection/)
**Type:** Web Application Attack Investigation  
**Logs Analyzed:** Apache Access Logs  
**Skills Demonstrated:** Log Analysis, Command Injection Investigation

---

## How to Use This Repository
Each project is contained in its own folder and includes:
- A detailed README documenting the investigation
- Step-by-step analysis mapped to supporting evidence and screenshots
- Evidence supporting conclusions
- Mitigation and security recommendations

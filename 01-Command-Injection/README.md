# Command Injection – High SIEM Alert

## 1. Alert / Detection Source
A High-severity SIEM alert was triggered indicating possible Command Injection activity.  
The alert flagged the string `ls` in a URL request. I received the alert, acknowledged it, and took ownership of the investigation.

---

## 2. Initial Analyst Hypothesis
Based on the alert, the initial hypothesis was that an attacker might be attempting command execution on a web server via URL or POST parameters.  
At this stage, it was unknown whether the alert reflected a true attack or a false positive.

---

## 3. Log Sources Reviewed
- SIEM alert logs
- Web server access logs
- Endpoint logs
- Email security mailbox

---

## 4. Step-by-Step Investigation

1. **Received and acknowledged the SIEM alert**  
   Took ownership of the case and began the investigation.

2. **Log analysis using source IP and alert time**  
   - Reviewed logs using the source IP and alert timestamp (Feb 27, 2022, 12:36 AM)  
   - POST parameters showed: `?s=skills`  
   - Full URL: `https://letsdefend.io/blog/?s=skills`  
   - HTTP response status: 200 OK, response size: 2577 bytes  
   - Comparison with other requests from the same IP confirmed normal browsing behavior  
   - No suspicious or malicious activity observed

3. **IP reputation and ownership analysis**  
   - VirusTotal score: 0  
   - IP ownership: Private / Reserved IP address  
   - No known malicious reputation

4. **Checked for authorized testing**  
   - Reviewed Email Security mailbox for planned tests involving the source or destination IP  
   - No emails indicating authorized testing found

5. **SIEM playbook execution and validation**  
   - Initiated SIEM playbook and documented findings  
   - Evidence supporting a false positive:
     - VirusTotal score showed no malicious indicators  
     - URL structure contained no command injection syntax  
     - POST parameter represented a legitimate user search  
     - Endpoint logs showed no commands executed on the host  
     - No malicious activity detected

6. **Traffic validation**  
   - Reviewed additional traffic from this IP  
   - Confirmed other activity was present, but none was malicious

7. **Incident closure**  
   - Entered final analyst comments in SIEM  
   - Closed the case

---

## 5. Evidence of Exploitation
- None — alert was determined to be a false positive  
- No command execution occurred  
- All HTTP responses were normal (200 OK)  

---

## 6. Conclusion
The investigation confirmed that the SIEM alert was a **false positive**:  
- The `ls` string detected in the URL was part of the word “skills”  
- User was browsing the letsdefend.io website  
- No malicious behavior observed at network, endpoint, or application levels  

---

## 7. Mitigation & Recommendations
- Maintain SIEM tuning to reduce false positives  
- Ensure analysts validate alerts with context and log correlation  
- Continue monitoring for real command injection attempts

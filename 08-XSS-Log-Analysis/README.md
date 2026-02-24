# Cross-Site Scripting (XSS) Log Analysis

## 1. Alert / Detection Source
The investigation was initiated after reviewing web server access logs for suspicious URL parameters containing client-side script content.

The activity was indicative of potential Cross-Site Scripting (XSS) attempts, based on the presence of encoded and unencoded script payloads within HTTP GET request parameters.
## 2. Initial Analyst Hypothesis
Based on the presence of script-based payloads within URL parameters, the initial hypothesis was that an attacker was attempting to execute a reflected Cross-Site Scripting (XSS) attack.

At this stage, it was unknown whether the payloads were successfully executed by the client or merely reflected in server responses without execution.
## 3. Log Sources Reviewed
- Web server access logs
## 4. Step-by-Step Investigation
1. Reviewed Apache web server access logs to identify the initial occurrence of suspicious URL parameters indicative of Cross-Site Scripting (XSS) activity.

   During log review, I identified a request containing keywords such as `alert` and `script`, which are commonly associated with XSS payloads. Based on this log entry, the attack start time was identified as 01/Mar/2022:08:53:20.
(Screenshot: screenshots/step-1-access-logs.png)
2. Analyzed the same Apache access log entry to identify the source IP address responsible for the malicious request.
(Screenshot: screenshots/step-2-filtered-requests.png)
   The source IP address associated with the XSS payload was identified as 192.168.31.183. This IP address was consistently observed in requests containing the malicious script content.

3. Evaluated HTTP response codes returned by the server to determine whether the XSS payload was successfully processed.
(Screenshot: screenshots/step-3-payload.png
   The server consistently returned HTTP 200 OK responses for requests containing the malicious payload. No defensive indicators were observed, including the absence of 400-series client errors, 403 Forbidden responses, WAF block messages, redirects, or server-side error responses. This indicated that the server processed the malicious request without blocking or sanitization.

4. Analyzed request and response behavior to classify the type of Cross-Site Scripting (XSS) attack observed.

   The malicious payload was present directly within the URL parameters and was processed by the server, which ruled out Stored XSS due to the absence of persistence mechanisms such as database writes or form submissions. The lack of client-side-only execution or DOM manipulation ruled out DOM-based XSS. Based on these indicators, the attack was classified as a Reflected Cross-Site Scripting (XSS) attempt.

## 5. Evidence of Exploitation
Payload was reflected
HTTP 200 responses observed
No sanitization detected
## 6. Conclusion
This investigation confirmed a successful reflected XSS attack identified through Apache access log analysis, including clear indicators of exploitation timing, attacker IP address, and attack classification.

## 7. Mitigation & Recommendations
Input validation
WAF rules

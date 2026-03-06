# IDOR (Insecure Direct Object Reference) Attack Investigation - Log Analysis

## Overview
This project demonstrates how Apache access logs were analyzed to identify activity consistent with an **Insecure Direct Object Reference (IDOR)** attack. The investigation focuses on identifying abnormal request patterns, analyzing HTTP response codes, and assessing whether an attacker may have attempted to enumerate user resources.

---

## Step 1: Identifying Suspicious Activity in Apache Logs

I began the investigation by reviewing Apache access logs to identify unusual request patterns that could indicate malicious behavior.

During the review, I observed that the IP address **192.168.31.174** was generating a high volume of requests within a very short time interval. This type of behavior is commonly associated with automated scanning tools or scripted attacks.

Further analysis showed that the attacker was repeatedly requesting different user IDs through the same endpoint. This pattern is consistent with **object enumeration**, which is commonly used when attempting to exploit an IDOR vulnerability.

### Evidence

![Step 1](images/idor-step1.png)

---

## Step 2: Analyzing Server Response Codes

After identifying the suspicious request patterns, I reviewed the HTTP response codes returned by the server.

The logs showed that the requests consistently received **HTTP 200 OK** responses, indicating that the server successfully processed the requests.

However, response codes alone do not confirm whether:

- Sensitive data was returned
- Authorization controls were bypassed
- The attacker successfully accessed other users' data

Further analysis of application logs or response content would be required to confirm data exposure.

### Evidence

![Step 2](images/idor-step2.png)

---

## Step 3: Investigation Summary

Through analysis of Apache access logs, I identified behavior consistent with a potential **IDOR attack attempt**.

Key findings from the investigation include:

- A single IP address (**192.168.31.174**) generating a high volume of requests within a short time window
- Systematic enumeration of multiple user IDs through the same endpoint
- Consistent **HTTP 200 OK** responses indicating the server processed each request successfully

Although the logs do not confirm whether sensitive data was exposed, the request pattern strongly suggests an attempted and potentially successful exploitation of an IDOR vulnerability.

---

## Skills Demonstrated

- Web server log analysis
- Identification of abnormal request patterns
- Attribution of suspicious activity to a source IP
- Analysis of HTTP response codes
- Investigation of web application security vulnerabilities

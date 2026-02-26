# IDOR (Insecure Direct Object Reference) Log Analysis

## 1. Alert / Detection Source
The investigation was initiated after reviewing web server access logs for suspicious object references passed through URL parameters. The activity suggested possible unauthorized access to resources by manipulating object identifiers.

---

## 2. Initial Analyst Hypothesis
Based on the presence of object identifiers within URL parameters, the initial hypothesis was that an attacker might be attempting to access resources belonging to other users by modifying object IDs without proper authorization checks.

At this stage, it was unknown whether the server enforced access controls or if the requests were successfully processed.

---

## 3. Log Sources Reviewed
- Web server access logs

---

## 4. Step-by-Step Investigation

1. Reviewed web server access logs to identify requests containing object identifiers passed via URL parameters.

2. Identified multiple requests where object IDs were modified manually, indicating potential enumeration of resources.

3. Correlated requests by source IP address and timestamp to confirm repeated access attempts involving different object IDs.

4. Analyzed server responses associated with the modified object ID requests.

5. Observed consistent HTTP 200 OK responses for requests targeting unauthorized object IDs, indicating the server processed the requests successfully.

6. Confirmed that no server-side authorization checks were enforced to validate whether the requesting user was permitted to access the referenced objects.

---

## 5. Evidence of Exploitation
- Unauthorized object IDs were accepted by the server  
- HTTP 200 OK responses returned for modified object references  
- Requested objects were successfully retrieved without access restrictions  

---

## 6. Conclusion
This investigation confirmed the presence of an **Insecure Direct Object Reference (IDOR)** vulnerability. The application failed to enforce server-side authorization checks, allowing access to resources by simply modifying object identifiers in the request.

---

## 7. Mitigation & Recommendations
- Enforce server-side authorization checks for all object references  
- Avoid exposing direct object identifiers in URLs  
- Implement access control validation based on user context  
- Log and monitor repeated object ID enumeration attempts

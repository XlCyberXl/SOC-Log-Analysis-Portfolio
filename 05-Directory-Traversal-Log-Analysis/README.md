# Directory Traversal Log Analysis

## 1. Alert / Detection Source
Web server access logs revealed suspicious URL requests attempting to access files outside the intended web root directory.

## 2. Initial Analyst Hypothesis
The presence of directory traversal patterns such as "../" within HTTP requests suggested that an attacker was attempting to manipulate file paths to access sensitive system files.

## 3. Log Sources Reviewed
- Web server access logs  
- HTTP request logs  

## 4. Step-by-Step Investigation
1. Identified HTTP GET requests containing directory traversal sequences such as "../" attempting to move outside the application’s directory structure.

2. Observed requests targeting sensitive files, indicating malicious intent rather than legitimate user behavior.

3. Reviewed HTTP response codes to determine whether the requests were successful. HTTP 200 responses would indicate potential file exposure, while HTTP 403 or 404 responses would indicate blocked attempts.

## 5. Evidence of Exploitation
- Directory traversal patterns ("../") in request URLs  
- Attempts to access files outside the web root  
- Abnormal request behavior inconsistent with legitimate traffic  

## 6. Conclusion
Log analysis confirmed directory traversal attempts within web server logs. The attacker attempted to manipulate URL paths to access restricted files outside the intended directory structure. This project demonstrates the ability to detect traversal patterns, analyze HTTP requests, and assess potential file exposure risks.

## 7. Mitigation & Recommendations
- Implement strict input validation  
- Use proper path normalization and sanitization  
- Restrict file permissions on sensitive files  
- Deploy Web Application Firewall (WAF) protections  

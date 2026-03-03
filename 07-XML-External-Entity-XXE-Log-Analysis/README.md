# XML External Entity (XXE) Log Analysis

## 1. Alert / Detection Source
Application logs revealed suspicious XML payloads containing DOCTYPE declarations and external entity definitions, indicating a potential XXE attack attempt.

## 2. Initial Analyst Hypothesis
The presence of external entity references within XML requests suggested that an attacker was attempting to exploit XML parsing functionality to retrieve sensitive server data.

## 3. Log Sources Reviewed
- Web server access logs  
- Application logs containing XML request payloads  

## 4. Step-by-Step Investigation
1. Identified HTTP POST requests containing XML data with DOCTYPE declarations and ENTITY definitions.

2. Observed external entity references attempting to access local system files or internal resources.

3. Reviewed HTTP response codes and application responses to determine whether the malicious XML payload was processed successfully.

## 5. Evidence of Exploitation
- DOCTYPE declarations within XML payloads  
- External entity definitions referencing local files  
- Abnormal or successful server responses following malicious payload submission  

## 6. Conclusion
Log analysis identified XML payloads consistent with XXE attack attempts. The attacker attempted to manipulate XML parsing to access sensitive data. This project demonstrates the ability to detect XML-based exploitation attempts and analyze application log behavior.

## 7. Mitigation & Recommendations
- Disable external entity processing in XML parsers  
- Use secure XML parsing configurations  
- Validate and sanitize XML input  
- Implement Web Application Firewall (WAF) protections  

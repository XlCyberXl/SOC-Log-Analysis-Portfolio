# Brute Force Attack Log Analysis

## 1. Alert / Detection Source
Authentication logs revealed multiple rapid login attempts from a single IP address, indicating potential brute force activity.

## 2. Initial Analyst Hypothesis
The high frequency and rapid timing of login attempts suggested automated behavior. It was likely that an attacker was attempting to brute force account credentials.

## 3. Log Sources Reviewed
- Authentication logs  
- Web server access logs  

## 4. Step-by-Step Investigation
1. Identified a single IP address (146.214.73.240) generating multiple login attempts within a very short timeframe. The speed and repetition exceeded normal human behavior, indicating automation.

2. Extracted and analyzed the associated User-Agent from the login requests. The User-Agent observed was:
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.5615.50 Safari/537.36

3. Reviewed HTTP response codes to determine whether the attack was successful. An HTTP 302 response was identified on 26/Apr/2023 at 21:44:03, indicating a successful authentication followed by a redirect.

## 5. Evidence of Exploitation
- High-frequency login attempts from a single IP  
- Consistent User-Agent across authentication attempts  
- HTTP 302 response confirming successful login  

## 6. Conclusion
This investigation confirmed a brute force attack conducted from IP address 146.214.73.240. Log analysis revealed automated credential attempts that ultimately resulted in a successful authentication. This project demonstrates the ability to detect brute force behavior, analyze login patterns, and determine attack success using HTTP response codes.

## 7. Mitigation & Recommendations
- Implement account lockout policies  
- Enforce multi-factor authentication (MFA)  
- Monitor for excessive failed login attempts  
- Create alert thresholds for abnormal authentication activity  

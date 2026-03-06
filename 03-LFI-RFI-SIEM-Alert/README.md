# Local File Inclusion (LFI) / Remote File Inclusion (RFI) – SIEM Alert Investigation

## 🔍 Project Overview
This project documents a high-severity SIEM investigation into a potential **Local File Inclusion (LFI)** and **Remote File Inclusion (RFI)** attack. As a SOC Analyst, I triaged the alert, performed threat intelligence lookups on the source IP, analyzed web traffic patterns, and determined the final outcome based on server response behaviors.


---

## 🛠️ Investigation Steps

### Step 1: Received and Acknowledged the SIEM Alert
I received a High-severity SIEM alert for a possible LFI attack. I took ownership of the case and initiated the investigation using the established SIEM playbook.

### Step 2: Reviewed Event Details and Identified Initial Red Flags
While reviewing the event details, I identified several critical indicators of malicious activity:
* **Reputation Check:** VirusTotal returned a score of **-18**, indicating highly malicious activity.
* **Geolocation:** Whois research confirmed the traffic originated from the **People’s Republic of China**, an external source.
* **URL Analysis:** The requested URL contained **directory traversal sequences**, a strong indicator of LFI/RFI attempts.

### Step 3: Investigated Destination Host Activity in Log Management
I searched the destination IP address (`172.16.17.13`) in log management to gather additional technical details:
* **Traffic Data:** The request used port **443 (HTTPS)** and the **GET** method.
* **Payload Confirmation:** The URL clearly showed directory traversal sequences.
* **Server Response:** The server returned an **HTTP 500 Internal Server Error**, indicating the request failed and the attack was not successful.

### Step 4: Checked for Authorized or Planned Testing
I cross-referenced the activity with the **Email Security** inbox to determine if this was part of a planned security test.
* **Result:** No evidence of a planned test was found for either the source or destination IP.

### Step 5: Completed SIEM Playbook Decision Points
After confirming this was not an authorized test, I documented the following decisions in the SIEM playbook:
* **Attack Confirmed:** Yes
* **Attack Type:** LFI / RFI
* **Planned Test:** No
* **Traffic Direction:** Internet → Company Network
* **Escalation Required:** No

### Step 6: Added Artifacts, Finalized Analysis, and Closed the Case
I added all relevant artifacts to the SIEM case. I confirmed that escalation to Tier 2 was not required because the attack failed, as evidenced by the 500 response code and 0 bytes returned. I entered my final notes and closed the case as a **True Positive (unsuccessful attack)**.

---

## 🏁 Final Outcome
This investigation confirmed a **true positive LFI/RFI attack attempt** originating from an external source. The attack was unsuccessful due to server-side error handling, and no escalation was required.

---

## 🛡️ Skills Demonstrated
* **SIEM Operations:** Full lifecycle management of high-severity alerts.
* **Threat Intelligence:** Adversary profiling using VirusTotal and WHOIS.
* **Traffic Analysis:** Interpreting directory traversal payloads and HTTP response codes.
* **Incident Response:** Applying standardized playbooks to verify and contain threats.

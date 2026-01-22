# Phase 4: Indicator Validation (IP Reputation & URL Analysis)

## Objective
The objective of this phase is to validate the indicators extracted in Phase 3 using **external intelligence and analysis tools**. This phase focuses on sender IP reputation and URL behavior analysis without making a final phishing verdict.

---

## Scope of Phase 4
This phase answers the following investigation questions:

- Is the sender IP blacklisted?
- Are URLs present in the email suspicious or malicious?

---

## Tools Used
- VirusTotal
- AbuseIPDB
- browserling.com
- urlscan.io (not applicable where URL is absent)

---

## 1. Sender IP Reputation Analysis

### Sample 1005 – Sender IP: `192.232.233.127`

#### VirusTotal Result
- Detection ratio: **0 / 92**
- No security vendor flagged this IP as malicious
- ASN: AS46606 (UnifiedLayer)

#### AbuseIPDB Result
- IP found in database: **Yes**
- Total reports: **5**
- Abuse confidence score: **0%**

**Final Assessment (Sample 1005 IP):**
- Sender IP is NOT blacklisted

---
📸 Screenshot evidence:
- VirusTotal IP analysis
<img width="1537" height="962" alt="image" src="https://github.com/user-attachments/assets/e6e6c3f6-27f8-4969-8037-a59bc76bd961" />

- AbuseIPDB IP report
<img width="1663" height="891" alt="image" src="https://github.com/user-attachments/assets/a4c429aa-8932-4cbc-98ab-0fe6a3a9a13d" />

---

### Sample 1006 – Sender IP: `103.255.97.80`

#### VirusTotal Result
- Detection ratio: **0 / 92**
- No security vendor flagged this IP as malicious
- ASN: AS31898 (Oracle-BMC)

#### AbuseIPDB Result
- IP found in database: **No**
- Abuse confidence score: **N/A**
- No abuse reports available

**Final Assessment (Sample 1006 IP):**
Sender IP is NOT blacklisted


📸 Screenshot evidence:
- VirusTotal IP analysis
<img width="1541" height="957" alt="image" src="https://github.com/user-attachments/assets/b7ae0ffc-b3f7-45a9-aec4-3a8017d3ffaa" />



- AbuseIPDB IP report
<img width="1715" height="903" alt="image" src="https://github.com/user-attachments/assets/31082bf5-0064-4151-9b11-aa772f65e712" />


---

## 2. URL Analysis

### Sample 1005 – URL Analysis
- No valid external URL found in the email body
- Only a placeholder anchor (`#CURL#`) and Base64-encoded image content observed

**URL Analysis Status:**
Not applicable – No external URL available for scanning


---

### Sample 1006 – URL Analysis

A representative URL extracted from the email body was analyzed using multiple tools.

#### VirusTotal (URL Scan)
- Detection ratio: **0 / 95**
- No security vendor flagged the URL as malicious
- Content type: `image/png`
- Multiple redirects observed

#### browserling.com (Behavioral Check)
- Primary tracking URL did not load
- Result: **“This page can’t be displayed”**
- Static asset URLs returned **Access Denied**

📸 Screenshot evidence:
- VirusTotal URL analysis
<img width="1554" height="920" alt="image" src="https://github.com/user-attachments/assets/89406d40-3d58-4adf-9323-4e9afeef9470" />


- browserling session output
<img width="1638" height="923" alt="image" src="https://github.com/user-attachments/assets/2049ff69-c907-4273-88a9-e70880c3df36" />
<img width="1527" height="939" alt="image" src="https://github.com/user-attachments/assets/db85da65-4a03-4864-b43a-b81634a3e6bf" />


**URL Analysis Summary (Sample 1006):**
No malicious detection observed, but tracking and redirection behavior confirmed


---

## Phase 4 Summary

| Indicator | Sample 1005 | Sample 1006 |
|--------|-------------|-------------|
Sender IP Blacklisted | No | No |
URL Present | Placeholder only | Yes |
URL Malicious | Not applicable | No (tracking behavior observed) |

---

## Phase Outcome

By the end of Phase 4:
- Sender IPs for both samples were validated and confirmed as not blacklisted
- URL analysis was completed where applicable
- No conclusions regarding phishing or legitimacy were made

The validated indicators from this phase will be correlated with infrastructure analysis in **Phase 5** to reach a final determination.

---

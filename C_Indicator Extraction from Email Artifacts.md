# Phase 3: Indicator Extraction from Email Artifacts (.eml)

## Objective
The objective of this phase is to extract **key forensic indicators** from two email samples using their raw `.eml` files. At this stage, the analysis is limited strictly to **information available within the email headers and body**. No reputation checks or verdicts are made in this phase.

---

## Email Samples Under Investigation

- **Sample 1005 (.eml)**
- **Sample 1006 (.eml)**

Both samples are analyzed using the same methodology to ensure an unbiased and consistent comparison.

---

## Tool Used

### EML Analyzer
The EML Analyzer tool is used to parse raw `.eml` files and extract:
- Sender information
- Sending domain
- Sender IP address
- Email authentication results
- URLs present in the email body

---

## Analysis Methodology

### Step 1: Upload `.eml` Files
Each `.eml` file was uploaded individually to the EML Analyzer tool, and the parsed output was reviewed for relevant indicators.

📸 Screenshot evidence:
- EML Analyzer output for Sample 1005  
- EML Analyzer output for Sample 1006  

---

## Extracted Indicators

### 1. Full Email Address of the Sender

- **Sample 1005:**  
  `noreply@att.net`

- **Sample 1006:**  
  `info@updates.policybazaar.com`

---

### 2. Domain Used to Send the Email (From / Return-Path)

- **Sample 1005:**  
  - From / Return-Path domain: `att.net`

- **Sample 1006:**  
  - From domain: `updates.policybazaar.com`  
  - Return-Path domain: `sco254.policybazaar.com`

---

### 3. Sender’s IP Address (From Headers)

- **Sample 1005:**  
  `192.232.233.127`

- **Sample 1006:**  
  `103.255.97.80`

---

### 4. SPF Authentication Result

- **Sample 1005:**  
  `SPF: None`

- **Sample 1006:**  
  `SPF: Pass`

---

### 5. URLs Found in Email Body

- **Sample 1005:**  
  URL present (placeholder observed in email body)

- **Sample 1006:**  
  Multiple URLs present (marketing, tracking, and unsubscribe links)

---

## Indicator Comparison Summary

| Indicator | Sample 1005 | Sample 1006 |
|--------|------------|-------------|
Sender Email Address | noreply@att.net | info@updates.policybazaar.com |
Sending Domain | att.net | updates.policybazaar.com |
Sender IP Address | 192.232.233.127 | 103.255.97.80 |
SPF Result | None | Pass |
URLs Present | Yes | Yes |

---

## Important Notes

- No IP reputation checks were performed in this phase
- No URL behavior analysis was performed
- No conclusions or classifications were made

All extracted indicators will be validated and correlated in **Phase 4 and Phase 5** before determining whether either email is phishing.

---

## Phase Outcome

By the end of this phase, we have:
- Extracted all required indicators directly from email artifacts
- Established a neutral comparison baseline between both samples
- Prepared structured input for reputation and infrastructure analysis in subsequent phases

This phase ensures that later decisions are **evidence-driven and defensible**.

---

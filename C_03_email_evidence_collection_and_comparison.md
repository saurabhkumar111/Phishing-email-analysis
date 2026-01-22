# Phase 3: Email Evidence Collection and Comparison (.eml Analysis)

## Objective
The objective of this phase is to collect and examine raw email evidence from two `.eml` files and perform a **neutral, indicator-based comparison**. At this stage, no assumptions are made about whether an email is phishing or legitimate. Classification will be performed only after technical validation in later phases.

---

## Email Samples Used

Two email samples are analyzed in this project:

1. **Sample 1005 (.eml)**
   - Email sample obtained for analysis
   - Source preserved in original `.eml` format
   - Classification pending

2. **Sample 1006 (.eml)**
   - Email sample obtained for analysis
   - Source preserved in original `.eml` format
   - Classification pending

Both samples are treated equally and analyzed using the same methodology to avoid bias.

---

## Tool Used

### EML Analyzer
The EML Analyzer tool is used to parse raw `.eml` files and extract structured information such as:
- Email headers
- Sender details
- Authentication results
- Embedded URLs

This allows analysis of email artifacts without altering the original evidence.

---

## Analysis Methodology

### Step 1: Upload Email Samples
- Upload **Sample 1005** to the EML Analyzer
- Upload **Sample 1006** to the EML Analyzer
- Preserve raw headers for reference and comparison

📸 Screenshot: EML Analyzer output for Sample 1005  
📸 Screenshot: EML Analyzer output for Sample 1006

---

## Extracted Indicators

For each sample, the following indicators are extracted:

### 1. Sender Email Address
- Extracted from the `From` header
- Used to assess sender identity consistency

### 2. Sending Domain
- Extracted from `From` and `Return-Path`
- Helps identify domain mismatches or alignment

### 3. Sender IP Address
- Extracted from `Received` headers
- Used later for reputation analysis

### 4. Email Authentication Results
- SPF result
- DKIM result (if present)
- DMARC result (if present)

### 5. Embedded URLs
- URLs extracted from the email body
- Used for link and behavior analysis in later phases

---

## Comparative Indicator Table

| Indicator | Sample 1005 | Sample 1006 |
|---------|-------------|-------------|
Sender Email Address | Extracted | Extracted |
Sending Domain | Identified | Identified |
Sender IP Address | Identified | Identified |
SPF Result | Recorded | Recorded |
Embedded URLs | Extracted | Extracted |

📸 Screenshot: Side-by-side header comparison (Sample 1005 vs Sample 1006)

---

## Initial Observations (Non-Conclusive)

At this stage:
- No assumptions are made about malicious or legitimate intent
- Observations are limited to **structural and configuration differences**
- Behavioral, reputation, and intent analysis will be performed in subsequent phases

This ensures that conclusions are **evidence-driven** rather than assumption-based.

---

## Why Neutral Comparison Is Important

Using neutral sample identifiers:
- Prevents analyst bias
- Reflects real-world SOC workflows
- Encourages indicator-based investigation
- Ensures defensible final conclusions

Email classification should only occur after correlating:
- Header analysis
- Authentication results
- IP reputation
- URL behavior

---

## Phase Outcome

By completing this phase, we establish:
- Proper handling of email evidence
- Consistent extraction of indicators from multiple samples
- A structured comparison framework
- A reliable foundation for reputation and behavior analysis

Final classification of Sample 1005 and Sample 1006 will be performed only after completing all technical validation phases.

---

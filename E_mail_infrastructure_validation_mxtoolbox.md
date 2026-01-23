# Phase 5: Mail Infrastructure Validation (MXToolbox)

## Objective
The objective of this phase is to validate the **email-sending infrastructure** of both samples using **MXToolbox**.  
This phase focuses on DNS, MX, and DMARC configuration to support the final classification decision.

---

## Tool Used

### MXToolbox – SuperTool
MXToolbox was used to perform:
- MX record lookup
- DNS record verification
- DMARC record presence and policy check

This phase provides **supporting evidence only** and does not independently determine phishing.

---

## 1. Infrastructure Analysis – Sample 1005

### Domain Checked
- **att.net**

### MXToolbox Results

**MX Records**
- MX record found:
  - `mx.att.mail.am0.yahoodns.net`
- Mail service provider: Yahoo Biz

**DNS Record**
- DNS record: **Found**

**DMARC Status**
- DMARC record: **Not found**
- DMARC policy: **Not enabled**

### Infrastructure Assessment (Sample 1005)

- Domain has valid MX and DNS records, but DMARC is not implemented.
Email authentication enforcement is weak.


📸 Evidence:
<img width="1523" height="884" alt="image" src="https://github.com/user-attachments/assets/5a8d24f9-7e59-49f5-99b8-cc4156fb98e3" />


---

## 2. Infrastructure Analysis – Sample 1006

### Domain Checked
- **updates.policybazaar.com**

### MXToolbox Results

**DNS Record**
- DNS record: **Not found**

**DMARC Status**
- DMARC record: **Found**
- DMARC policy: **Enabled (Quarantine / Reject)**

### Infrastructure Assessment (Sample 1006)

-DMARC enforcement is enabled, indicating a stronger email authentication posture.
DNS record absence suggests the subdomain is not intended for direct mail reception.


📸 Evidence:
<img width="1516" height="726" alt="image" src="https://github.com/user-attachments/assets/a4459c8b-f170-4005-91ff-90d4b407deb9" />



---

## Phase 5 Comparison Summary

| Indicator | Sample 1005 | Sample 1006 |
|--------|------------|-------------|
MX Record | Present | Not applicable |
DNS Record | Found | Not found |
DMARC Record | Not found | Found |
DMARC Policy | Not enabled | Quarantine / Reject |
Infrastructure Strength | Weak | Strong |

---

## Phase Outcome

By completing Phase 5:
- Mail infrastructure differences between both samples were identified
- Sample 1006 demonstrates stronger authentication enforcement
- Sample 1005 lacks DMARC protection, reducing trustworthiness

These findings will be correlated with:
- Header indicators (Phase 3)
- Reputation analysis (Phase 4)
- Content and behavior patterns

Final classification will be provided in **Phase 6**.

---

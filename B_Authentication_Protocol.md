# Phase 2: Email Authentication Protocols (Theory)

## Objective
The objective of this phase is to understand how email authentication mechanisms work to prevent spoofing and impersonation attacks. This theoretical foundation is essential to correctly interpret email headers during phishing analysis.

---

## Why Email Authentication is Important

Email authentication protocols are designed to:
- Verify the legitimacy of the sender
- Prevent domain spoofing
- Reduce phishing and spam
- Help receiving mail servers decide whether to accept, reject, or flag emails

Phishing attacks often attempt to bypass or abuse weaknesses in these mechanisms.

---

## 1. SPF (Sender Policy Framework)

### What is SPF?
SPF is an email authentication protocol that specifies **which mail servers are authorized to send emails on behalf of a domain**.

It works by checking the sender’s IP address against the SPF record published in the domain’s DNS.

### How SPF Works
1. Receiving mail server extracts the sender domain
2. DNS lookup is performed for the domain’s SPF record
3. Sender IP is compared against authorized IPs
4. A result is returned

### Common SPF Results
- **Pass** – Sender IP is authorized
- **Fail** – Sender IP is not authorized
- **Neutral / SoftFail** – No strict policy defined
- **None** – No SPF record found

### Limitation of SPF
- SPF checks only the **MAIL FROM / Return-Path**, not the visible “From” address
- Attackers can still spoof display names

---

## 2. DKIM (DomainKeys Identified Mail)

### What is DKIM?
DKIM ensures that the **email content has not been altered in transit** and confirms that the email was authorized by the sending domain.

It uses **cryptographic signatures** added to the email header.

### How DKIM Works
1. Sending server signs the email with a private key
2. Public key is published in DNS
3. Receiving server verifies the signature using the public key
4. If content matches, DKIM passes

### DKIM Results
- **Pass** – Email integrity verified
- **Fail** – Email content modified or signature invalid
- **None** – DKIM not configured

### Limitation of DKIM
- Does not validate sender intent
- A compromised domain can still send phishing emails with valid DKIM

---

## 3. DMARC (Domain-based Message Authentication, Reporting & Conformance)

### What is DMARC?
DMARC builds on SPF and DKIM and tells receiving servers **how to handle authentication failures**.

It also enables **reporting** to domain owners.

### DMARC Policies
- **none** – Monitor only
- **quarantine** – Send to spam
- **reject** – Reject the email

### How DMARC Works
DMARC requires **alignment** between:
- Visible “From” address
- SPF or DKIM authenticated domain

If alignment fails, DMARC policy is applied.

---

## How Attackers Bypass Email Authentication

Attackers use several techniques to bypass or abuse these protocols:

- Using domains with **weak or misconfigured SPF**
- Sending emails from domains with **no DMARC policy**
- Compromising legitimate domains with valid SPF/DKIM
- Display name spoofing (fake sender name)
- Using lookalike domains (typosquatting)

Even when SPF or DKIM passes, an email can still be phishing.

---

## Why Authentication Results Alone Are Not Enough

A common misconception is that:
> “SPF pass means the email is safe”

In reality:
- Authentication verifies **sender legitimacy**, not **intent**
- Phishing emails can pass SPF, DKIM, and DMARC
- Analysts must correlate authentication with:
  - IP reputation
  - URL analysis
  - Email content

---

## Phase Outcome

By completing this phase, we establish:
- Clear understanding of SPF, DKIM, and DMARC
- Ability to interpret authentication results in email headers
- Awareness of how attackers bypass defenses

This knowledge is critical for accurate phishing email analysis in subsequent phases.

---

# Suspicious Email Attachment - Fake Stripe Invoice
----------------------------------------------

**Date:** 02/09/2026
**Data Source:** Simulated SIEM Alert (Email Security/ SOC Training Lab)
**Severity:** High
**Status:** Closed
----------------------------------------------

# Affected User

- Mark Phillips - Finance Director
----------------------------------------------

# Incident Summary 

A suspicious email claiming to be a Stripe payment confirmation was received by a finance executive. The email originated from a spoofed domain and included a password-protected RAR attachment, indicating a potential malware delivery attempt.
----------------------------------------------

# Investigative Details

Indicators Observed 

- Sender domain: stripe-payments[.]xyz
- Attachment: Invoice.rar (password protected)
- Social engineering language ("payment succeeded", urgency)
- Mismatch between sender domain and legitimate Stripe domains.

Analysis Performed

- Reviewed sender domain legitimacy
- Assessed attachment type and delivery method
- Determined attachment contained a malicious payload
----------------------------------------------

# MITRE ATT&CK Mapping
- T1566.001 - Phishing: Spear phishing Attachment
- T1204.002 - User Execution: Malicious File
----------------------------------------------

# Response Actions Taken

- Blocked sender domain
- Prevented delivery of attachment
- Escalated as phishing incident
- Documented indicators of compromise
----------------------------------------------

# Outcome

The phishing attempt was successfully identified and blocked before the attachment could be opened, preventing potential malware execution and financial compromise.
----------------------------------------------

# Lessons Learned

- Finance roles are high value phishing targets
- Password protected archives are common malware delivery techniques
- Domain validation is critical for invoice related emails.

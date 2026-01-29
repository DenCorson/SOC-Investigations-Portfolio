# Employee Phishing Attempt- Attempt Investigated
----------------------------------------------

**Date:** 01/29/2026
**Data Source:** Email Security Logs (SIEM, SPLUNK) 
**Severity:** Low
**Status:** Closed
----------------------------------------------

# Scenario

Alert triggered by targeted user receiving email from outside entity, requesting sensitive information
from user to obtain undisclosed amount of money from unknown relative.
----------------------------------------------

# The 5 W's

**Who**
- Recipient/Target: support@tryhatme.com
- Sender/Threat Actor: eileen@trendymillineryco.me
- Investigating.....

**What**
- Threat Actor, eileen@trendymillineryco.me, sent target, support@tryhatme.com, an email disclosing that their
unknown relative had left an inheritance for them. User's banking information (PII) is requested in order to obtain
inheritance.

**When**
- January 29 2026

**Where** 
- Company email

**Why**
- Threat actor seeks to play on the emotions of target in order to obtain banking information for
nefarious means. TA being vague and not disclosing name or any important details of relative mentioned
keeps targets guard low.
----------------------------------------------

## Investigation Steps
1. Queried TA's (eileen@trendymillineryco.me) email domain on company network
2. Results pulled and displayed one email from TA displaying the TA had attempted to make contact with only one
   employee from network.
3. Searched for outbound email replies from support@tryhatme.com to eileen@trendymillineryco.me.
4. No replies or follow up communication observed.
5. **Verified** no contact was made with threat. 
----------------------------------------------

## Classification

**Classification:** True Positive - Phishing (Social Engineering)

- Threat Actor attempted to phish the target for sensitive banking information using social engineering.
- Alert was flagged due to TA email being unknown.
- User Successfully did not reply or contact TA back

----------------------------------------------

## Outcome & Recommendations

- Alert successfully notified network of suspicious email
- Add sender domain to email blocklist
- Continue monitoring for similar inheritance-based phishing attempts
- Reinforce phishing awareness training for finance related social engineering. 
- No recommendation of escalation.



















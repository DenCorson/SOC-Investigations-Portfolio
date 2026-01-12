# Inbound Phishing Email - Suspicious URL Blocked
**Case ID** 8815
**Date:** 2026-01-04
**Data Source:** Email Logs, Firewall Logs (Splunk SIEM)
**Severity:** Low
**Status:** Closed

--------------------------------------------------

## Scenario
An inbound email containing a suspicious URL was delivered to an internal user.
Investigation was required to determine if link was accessed and if any endpoints were
compromised.

--------------------------------------------------

## The 5 W's

**Who**
- Recipient: h.harris@thetrydaily.thm
- Sender (Threat Actor/TA): urgents@amazon.biz

**What**
- Inbound phishing email containing a suspicious malicious URL attempting to lure target
  into accessing compromised website on internal endpoint.

**When**
- January 4, 2026

**Where**
- External email infrastructure -> email gateway -> internal endpoint
- SIEM logs reviewed for outbound email activity
- Firewall logs reviewed for outbound web activity

**Why**
- Financially motivated phishing attempt levarging brand impersonation

--------------------------------------------------

## Investigation Steps

1. Queried email logs using wildcard searches to isolate suspicious message.
2. Identified the embedded URL and searched firewall logs using a known segment of the
URL.
3. Verified firewall action was **Blocked** with application type **web-browsing**.
4. Reviewed Source IP and Destination IP fields to confirm traffic direction.

--------------------------------------------------

##  Classification 

**Classification:** True Positive - Phishing (URL-Based)

- Email originated from an untrusted sender impersonating a known brand.
- Embedded URL matched firewall logs associated with blocked traffic.
- Firewall successfully prevented access to the malicious destination.
- No evidence of endpoint compromise observed.

--------------------------------------------------

## Outcome & Recommendations

- Firewall controls successfully blocked the malicious URL.
- No user interaction beyond attempted access observed.
- Continue enforcing URL filtering and sender monitoring policies.

--------------------------------------------------


## Notes

- Blocked threats still qualify as ** True Positives** due to confirmed malicious behavior.

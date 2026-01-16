# Outbound Blacklisted Website Attempt - Attempt Blocked 
----------------------------------------------

**Date:**  01/05/2026
**Data Source:** FireWall Logs (Splunk SIEM)
**Severity:** Low
**Status:** Closed
----------------------------------------------

# Scenario

Firewall Alert was triggered due to a internal user attempting to access suspcious URL
Link. Targeted link was on companies blacklist. Firewall successfully blocked user endpoint access attempt.
----------------------------------------------

# The 5 W's

**Who**U
- Source IP:  10.20.2.17
- Restricted URL: http://bit.ly/3sHkX3da12340

**What**
- User *Source IP: 10.20.2.17* attempted to access blacklisted URL *http://bit.ly/3sHkX3da12340* compromising network.

**When**
 - Janaury 05, 2026

**Where** 
- Firewall logs reviewed for outbound web activity
- Virustotal scan URL for malicious data (Virustotal confirmed)

**Why**
- User unaware of restricted/blocked websites for network
----------------------------------------------

## Investigative Steps
1. Queried for Blocked web access results with Firewall Rule blocked.
2. **Identified** **blocked** result containing suspicious URL.
3. **Retrieved** Source IP of user attempting to access blacklisted site.
4. **Investigated** suspicious URL with External Threat intelligence and malware analysis.
5. **Confirmed** URL as Malicious/Phishing
7. **Verified** Firewall correctly identified and denied endpoint access to site
----------------------------------------------

##  Classification 

**Classification:** True Positive - Phishing (URL-Based)

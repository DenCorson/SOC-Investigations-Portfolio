# Process Creation Alert - Creation Investigated
----------------------------------------------

**Date:** 02/08/2026
**Data Source:** Sysmon (SIEM, SPLUNK)
**Severity:** Low
**Status:** Closed
 ----------------------------------------------

# Scenario

Alert triggered on Sysmon from process creation (Event Code 1) at 8:12:28.462 PM from TrustedInstaller.exe
----------------------------------------------

# The 5 W's

**Who**
- host.name: win-3459
- process.name: TrustedInstaller.exe
- process.pid:3577
- process.parent.name: services.exe
- process.parent.pid: 3506


**What**
- System Monitor (Sysmon) sent notification for process creation from a child process (PID 3506, TrustedInstallere.exe)


**When**
- February 08 2026

**Where**
-  process working directory: C:\Windows\system32\

**Why**
- Acitivty intiated by automated Windows servicing or maintenance operations.
----------------------------------------------

## Investigation Steps

1. Reviewed Sysmon Event Code 1 (Process Create) alerts.
2. Located alert in question by Date and Time
3. Identified child process: TrustedInstaller.exe
4. Verified that process command line directories C:\Windows\servicing\TrustedInstaller.exe
5. Queried for additional TrustedInstaller.exe alerts from Sysmon 
6. Identified additional alert at 8:38:41.462 PM (26 minutes apart) on another host (host name win-3449)
7. child process (TrustedInstaller.exe) reflects parent process as services.exe, similarity between alert in question
8. Searched Sysmon logs for post activites of child process (TrustedInstaller.exe)
	* process.parent.namme="*Trusted*"
9. No results.
10. Searched for additional events from child process with Process Identification (PID) lifecyle
	* process.pid="3577"
11. Results displayed single event, which was the intial alert at 8:12:28.462
12. Tuned searches to host win-3459
14. No registry modification, network activity, or file creation confirmed.
13. Confirmed suspicious activity occurrence on host and PID
14. Determine no activity aligned with Host, activity aligns with Windows servicing behavior.
----------------------------------------------

## Outcome & Recommendations

- Alert investigated and determined to be benign activity. Process creation event involved with TrustedInstaller.exe, initiated by services.exe, called from legitimate Windows system direction. Malicious behavior not identified.

- No remediation action required.
- Continue monitoring Sysmon process creation for anomalous behavior or execution.

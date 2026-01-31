# Process Creation Alert - Creation Investigated
----------------------------------------------

**Date:** 01/30/2026
**Data Source:** Sysmon (SIEM, SPLUNK)
**Severity:** Low
**Status:** Closed
----------------------------------------------

# Scenario

Alert triggered on Sysmon from Process creation Event Code 1 at 4:26:16.677 AM. 
----------------------------------------------

# The 5 W's

**Who**
- host.name: win-3459
- process.name: TrustedInstaller.exe
- process.parent.name: services.exe

**What**
- System Monitor (Sysmon) alerted from the creation of the child process (TrustedInstaller.exe) from parent process(services.exe) 

**When**
- January 30 2026

**Where**
- process.working_directory: C:\Windows\system32\

**Why**
- Acitivity consistent with automated Windows servicing or maintenance operations.
----------------------------------------------


## Investigation Steps

1. Reviewed Sysmon EventCode 1 (Process Create) alert.
2. Identified child process: TrustedInstaller.exe.
3. Identified parent process: Services.exe.
4. Noted execution path and working directory under Windows system locations.
5. Confirmed parent -> child relationship using
	- process.parent.name
	- process.parent.pid
	- process.pid
6. Validated that services.exe is a legitimate Service Control Manager process.
7. Searched for additional executions using wildcard search (*Trusted*).
8. Identified two occurrences within the same day, 30 minutes apart.
9. Observed different parent PIDs, consistent with separate service instances or restarts.
10. Searched for additional processes spawned by TrustedInstaller.exe.
11. Searched using:
 - process.parent.name="TrustedInstaller.exe"
 - Host + PID correlation
12. Found no child processes created by TrustedInstaller.exe.
13. Tuned searches to affected host win-3459 to reduce noise.
14. Confirmed no additional suspicious activity tied to the same PID or time window.
15. Evaluated execution context (system-level process, early morning timeframe).
16. Found no registry modifications, file creation events, or network activity tied to the process.
17. Determine no activty aligned with Windows servicing behavior.

----------------------------------------------

## Classification

**Classification:** False Positive - Process Creation 

- Process.parent.name (Services.exe) launched child process.pid (TrustedInStaller.exe) during 
routinely expected system behavior. Based on absence of malicious indicators and expected system behavior, 
classified the alert as a False Positive.

----------------------------------------------

## Outcome & Recommendations

- The alert was investigated and determined to be benign system activity. The process creation event involving TrustedInstaller.exe was initiated by services.exe from a legitimate Windows system directory. No indicators of malicious behavior was identified, including the absence of suspicious child processes, registry modifications, file creation events, or network activity. The alert was closed as a false positive.

- No remediation actions requred.
- Continue monitoring Sysmon process creation events for anomalous parent-child relationships or abnormal execution paths.

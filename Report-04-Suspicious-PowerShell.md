# Suspicious PowerShell Execution Investigation Report

## Incident Overview

**Alert Name:** Suspicious PowerShell Activity Detected

**Severity:** High

**Attack Type:** PowerShell Execution

**MITRE ATT&CK Tactic:** Execution

---

## Executive Summary

A suspicious PowerShell script was detected on a user workstation. The script was located within the Downloads directory and displayed behavior commonly associated with malware delivery and post-exploitation activities.

The activity required immediate investigation due to the risk of malicious code execution and unauthorized system access.

---

## Alert Details

| Field | Value |
|---------|---------|
| User | Tony |
| File Name | payload_1.ps1 |
| File Path | C:\Users\LetsDefend\Downloads\payload_1.ps1 |
| Severity | High |
| Attack Type | Suspicious Script Execution |

---

## Investigation Findings

### User Analysis

The activity was executed under the user account:

Tony

### File Analysis

The following PowerShell script was identified:

```text
C:\Users\LetsDefend\Downloads\payload_1.ps1
```

The script originated from the Downloads directory, which is frequently used during phishing and malware delivery campaigns.

### Security Concerns

PowerShell can be abused to:

- Download malware
- Execute malicious commands
- Create new users
- Establish persistence
- Disable security controls
- Collect sensitive information

### Indicators Observed

- Suspicious PowerShell script
- Execution attempt
- File located in Downloads folder
- Potential malware delivery activity

---

## Potential Impact

If executed successfully, the script could:

- Download additional malware
- Execute attacker commands
- Create unauthorized accounts
- Escalate privileges
- Establish persistence
- Steal sensitive information

---

## MITRE ATT&CK Mapping

### Execution

**T1059.001 - PowerShell**

The attacker attempted to execute commands using PowerShell.

### Persistence

**T1136 - Create Account**

Attackers may create accounts for future access.

### Discovery

**T1082 - System Information Discovery**

Attackers may gather information about the host.

### Collection

**T1005 - Data from Local System**

Sensitive files may be collected.

---

## Incident Classification

**Classification:** True Positive - Suspicious PowerShell Activity

The activity demonstrated characteristics commonly associated with malicious PowerShell execution.

---

## Containment Actions

1. Isolate the affected endpoint.
2. Terminate suspicious PowerShell processes.
3. Block malicious indicators.
4. Review user activity.
5. Search for additional payloads.

---

## Eradication

- Remove malicious scripts.
- Delete persistence mechanisms.
- Remove unauthorized accounts.
- Perform a full malware scan.

---

## Recovery

- Restore affected systems if required.
- Validate system integrity.
- Reset compromised credentials.
- Continue monitoring for suspicious activity.

---

## Lessons Learned

Organizations should:

- Restrict PowerShell usage where possible.
- Enable PowerShell logging.
- Monitor script execution activity.
- Implement application control policies.
- Conduct user awareness training.

---

## Conclusion

A suspicious PowerShell script was detected and investigated. The activity exhibited behavior consistent with malware execution techniques and should be treated as a security incident until proven otherwise.

---

**Author:** Talha Imran

**Role:** SOC Analyst

**Platform:** LetsDefend

**Status:** Investigation Completed

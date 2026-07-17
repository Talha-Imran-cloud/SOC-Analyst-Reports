# Malicious Macro Document Investigation Report

## Incident Overview

**Alert Name:** Malicious Macro Execution Detected

**Severity:** High

**Attack Type:** Malicious Document / Macro-Based Attack

**MITRE ATT&CK Tactic:** Initial Access

---

## Executive Summary

A Microsoft Word document containing embedded macros was detected on a user workstation. The document was delivered through a phishing campaign and attempted to persuade the victim to enable macro execution.

Macro-enabled documents are commonly used by threat actors to execute malicious code, download malware, and establish unauthorized access within an environment.

---

## Alert Details

| Field | Value |
|---------|---------|
| User | Jayne |
| File Name | edit1-invoice.docm |
| File Type | Macro Enabled Document |
| File Path | C:\Users\LetsDefend\Downloads\edit1-invoice.docm |
| Severity | High |

---

## Investigation Findings

### User Analysis

The suspicious activity was observed on:

Jayne

### File Analysis

The following document was detected:

```text
C:\Users\LetsDefend\Downloads\edit1-invoice.docm
```

The file extension:

```text
.docm
```

indicates a Microsoft Word document with macro functionality enabled.

### Threat Indicators

The document displayed several malicious characteristics:

- Macro-enabled file
- Delivered through phishing
- Located within Downloads directory
- Potential code execution capability
- Potential malware delivery mechanism

### Security Concerns

If a user enables macros:

- PowerShell may be launched
- Additional malware may be downloaded
- Unauthorized commands may execute
- Persistence may be established
- Sensitive information may be stolen

---

## Potential Impact

Successful execution could allow an attacker to:

- Gain initial access
- Download additional malware
- Create persistence mechanisms
- Escalate privileges
- Steal credentials
- Exfiltrate company data

---

## MITRE ATT&CK Mapping

### Initial Access

**T1566.001 - Phishing Attachment**

The attacker attempted to gain access through a malicious attachment.

### Execution

**T1204.002 - User Execution: Malicious File**

The victim is required to open and interact with the file.

### Command and Scripting Interpreter

**T1059.001 - PowerShell**

Macros frequently launch PowerShell for further malicious activity.

### Persistence

**T1136 - Create Account**

Attackers may establish persistence after successful compromise.

---

## Incident Classification

**Classification:** True Positive - Malicious Macro Document

The document exhibits characteristics commonly associated with phishing and malware delivery campaigns.

---

## Containment Actions

1. Remove the malicious document.
2. Isolate affected endpoints if execution occurred.
3. Block associated indicators.
4. Scan the endpoint for malware.
5. Review PowerShell execution logs.
6. Investigate for persistence mechanisms.

---

## Eradication

- Delete malicious files.
- Remove malware components.
- Remove unauthorized accounts.
- Remove persistence artifacts.
- Perform full endpoint scanning.

---

## Recovery

- Restore affected systems if required.
- Reset compromised credentials.
- Monitor for suspicious activity.
- Validate system integrity.

---

## Lessons Learned

Organizations should:

- Disable unnecessary macro execution.
- Implement email security controls.
- Train employees on phishing awareness.
- Restrict script execution policies.
- Monitor PowerShell activity.

---

## Conclusion

A malicious macro-enabled document was detected and investigated. The document was capable of executing attacker-controlled code and delivering additional malware. Immediate containment and endpoint review were recommended to prevent compromise.

---

**Author:** Talha Imran

**Role:** SOC Analyst

**Platform:** LetsDefend

**Status:** Investigation Completed

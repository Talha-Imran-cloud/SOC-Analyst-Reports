# SharePoint Remote Code Execution (RCE) Investigation Report

## Incident Overview

**Alert Name:** SOC342 - CVE-2025-53770 SharePoint ToolShell Auth Bypass and RCE

**Severity:** Critical

**Event ID:** 320

**Attack Type:** Web Attack

**MITRE ATT&CK Tactic:** Initial Access

**MITRE ATT&CK Technique:** Exploit Public-Facing Application (T1190)

---

## Executive Summary

A critical alert was generated indicating a possible exploitation attempt of the SharePoint ToolShell vulnerability (CVE-2025-53770). The attack targeted a public-facing SharePoint server using a suspicious unauthenticated POST request.

The request contained characteristics associated with ToolShell exploitation, including a spoofed referrer and a large payload size. Successful exploitation could allow an attacker to execute arbitrary code on the target server and gain unauthorized access.

---

## Alert Details

| Field | Value |
|---------|---------|
| Hostname | SharePoint01 |
| Source IP | 107.191.58.76 |
| Destination IP | 172.16.20.17 |
| HTTP Method | POST |
| Event ID | 320 |
| Severity | Critical |
| Attack Type | Web Attack |

---

## Investigation Findings

### Source IP Analysis

The source IP address:

107.191.58.76

initiated a suspicious HTTP POST request against the SharePoint server.

### Target Analysis

The destination server:

172.16.20.17

hosts a SharePoint application exposed to network traffic.

### Suspicious Indicators

The alert identified multiple indicators associated with exploitation attempts:

- Unauthenticated POST request
- Suspicious ToolPane.aspx access
- Large payload size
- Spoofed HTTP referrer
- Known CVE exploitation pattern

### Potential Impact

If the attack succeeds, an attacker may:

- Execute arbitrary commands
- Gain unauthorized access
- Deploy malware
- Create new administrative accounts
- Establish persistence
- Steal sensitive data
- Move laterally within the environment

---

## MITRE ATT&CK Mapping

### Initial Access
**T1190 - Exploit Public-Facing Application**

The attacker attempted to exploit a vulnerability in an externally accessible SharePoint application.

### Execution
**T1059 - Command and Scripting Interpreter**

A successful exploit could lead to command execution on the server.

### Persistence
**T1136 - Create Account**

An attacker may create additional accounts to maintain access.

### Credential Access
**T1556 - Modify Authentication Process**

Attackers may modify authentication mechanisms to bypass security controls.

---

## Incident Classification

**Classification:** True Positive - Exploitation Attempt

The activity matches known indicators associated with SharePoint ToolShell exploitation attempts and should be treated as a legitimate security incident until proven otherwise.

---

## Containment Actions

The following actions are recommended:

1. Block the source IP address.
2. Isolate the affected SharePoint server if compromise is suspected.
3. Review SharePoint logs for successful exploitation activity.
4. Check for suspicious PowerShell or command execution.
5. Review newly created accounts.
6. Investigate privilege escalation activity.
7. Verify MFA and authentication settings.
8. Apply vendor security patches immediately.

---

## Eradication

- Remove malicious files if discovered.
- Delete unauthorized accounts.
- Remove persistence mechanisms.
- Patch vulnerable SharePoint components.
- Conduct a full malware scan.

---

## Recovery

- Restore affected systems if required.
- Validate SharePoint functionality.
- Monitor logs for recurring activity.
- Verify system integrity before returning to production.

---

## Lessons Learned

Organizations should:

- Maintain timely patch management.
- Monitor web application logs continuously.
- Deploy Web Application Firewall (WAF) protections.
- Implement threat detection and alerting.
- Conduct regular vulnerability assessments.

---

## Conclusion

A critical SharePoint exploitation attempt targeting CVE-2025-53770 was detected. The attack displayed characteristics consistent with ToolShell exploitation techniques. Immediate investigation, containment, and patching actions are required to prevent unauthorized access and potential compromise of organizational resources.

---

**Author:** Talha Imran

**Role:** SOC Analyst

**Platform:** LetsDefend

**Status:** Investigation Completed

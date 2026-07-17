# RDP Brute Force Investigation Report

## Alert Information

- Alert Name: RDP Brute Force Detected
- Event ID: 234
- Severity: Medium
- Source IP: 218.92.0.56
- Destination IP: 172.16.17.148
- Protocol: RDP

---

## Incident Summary

A brute force attack was detected against an RDP service. The attacker attempted multiple logins using different usernames from a single source IP address.

---

## Investigation

The source IP address was identified as:

218.92.0.56

The destination host was:

Matthew

Multiple failed login attempts were observed.

---

## MITRE ATT&CK

- Tactic: Initial Access
- Technique: Brute Force (T1110)

---

## Impact

If successful, the attacker could gain unauthorized access and perform lateral movement, privilege escalation, persistence, and data theft.

---

## Containment

- Blocked malicious IP
- Reviewed login activity
- Checked for successful logins
- Reset credentials if required

---

## Conclusion

The alert was determined to be a True Positive brute force attempt. Further investigation should confirm whether the attacker successfully authenticated.

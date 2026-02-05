# TA0008 – Lateral Movement

## Overview

**Lateral Movement** represents techniques adversaries use to **move through an environment** by leveraging credentials, remote services, and trust relationships. After discovery and credential access, attackers attempt to access additional systems to expand control.

In **KQL Hunter**, Lateral Movement hunting focuses on detecting **abnormal remote authentications, suspicious SMB/RDP activity, pass‑the‑hash/ticket behavior, and cloud‑to‑cloud movement** across identity, endpoint, and network telemetry.

---

## Why Lateral Movement Matters

- Enables **rapid environment compromise**
- Often follows credential access
- Harder to detect than initial access
- Key indicator of **active intrusion**

---

## Top Data Sources for Lateral Movement Hunting

Lateral movement detection relies on authentication, network, and endpoint telemetry:

| Priority | Data Source                     | Table Name            | Use Case               |
| -------- | ------------------------------- | --------------------- | ---------------------- |
| ⭐ 1      | Windows Security Logs           | `SecurityEvent`       | NTLM / Kerberos logons |
| ⭐ 2      | Defender for Endpoint – Network | `DeviceNetworkEvents` | SMB / RDP traffic      |
| ⭐ 3      | Azure AD Sign-in Logs           | `SigninLogs`          | Cloud lateral movement |
| ⭐ 4      | Network Devices                 | `CommonSecurityLog`   | East‑west traffic      |
| ⭐ 5      | Defender for Endpoint – Process | `DeviceProcessEvents` | Remote execution tools |

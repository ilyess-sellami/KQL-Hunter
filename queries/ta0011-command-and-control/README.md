# TA0011 – Command and Control

## Overview

**Command and Control (C2)** represents techniques adversaries use to **communicate with compromised systems** to issue commands, receive data, and maintain control. Once established, C2 enables attackers to pivot, exfiltrate data, and deploy additional payloads.

In **KQL Hunter**, Command and Control hunting focuses on detecting **beaconing behavior, suspicious outbound connections, malicious domains, protocol abuse, and living-off-the-land binaries used for C2 traffic** across endpoint, network, and DNS telemetry.

---

## Why Command and Control Matters

- Indicates active attacker control
- Enables every post-compromise action
- Often persists for long periods
- High-value target for containment

---

## Primary Command and Control Techniques (MITRE ATT&CK)

Common techniques covered in this section include:

- **T1071 – Application Layer Protocol**
- **T1095 – Non-Application Layer Protocol**
- **T1105 – Ingress Tool Transfer**
- **T1573 – Encrypted Channel**
- **T1568 – Dynamic Resolution**

Each query is **mapped directly to a MITRE C2 technique**.

---

## Top Data Sources for Command and Control Hunting

C2 detection relies on network behavior and communication patterns:

| Priority | Data Source                     | Table Name            | Use Case                |
| -------- | ------------------------------- | --------------------- | ----------------------- |
| ⭐ 1      | Defender for Endpoint – Network | `DeviceNetworkEvents` | Beaconing & outbound C2 |
| ⭐ 2      | DNS Logs                        | `DnsEvents`           | Suspicious domains      |
| ⭐ 3      | Network / Firewall Logs         | `CommonSecurityLog`   | Egress traffic          |
| ⭐ 4      | Defender for Endpoint – Process | `DeviceProcessEvents` | LOLBins for C2          |
| ⭐ 5      | Defender for Endpoint – File    | `DeviceFileEvents`    | Payload download        |

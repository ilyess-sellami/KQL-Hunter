# TA0010 – Exfiltration

## Overview

**[Exfiltration](https://attack.mitre.org/tactics/TA0010/)** represents techniques adversaries use to **steal data out of the environment**. After collecting sensitive information, attackers transfer it to external systems using network channels, cloud services, or covert methods.

In **KQL Hunter**, Exfiltration hunting focuses on detecting **abnormal outbound data transfers, suspicious cloud uploads, DNS tunneling, and misuse of trusted services** across network, endpoint, and cloud telemetry.

---

## Why Exfiltration Matters

- Indicates **confirmed data loss**
- Often follows collection and staging activity
- Frequently abuses **legitimate services**
- Early detection can limit breach impact

---

## Top Data Sources for Exfiltration Hunting

Exfiltration detection relies heavily on outbound network visibility:

| Priority | Data Source                     | Table Name            | Use Case                    |
| -------- | ------------------------------- | --------------------- | --------------------------- |
|  01      | Defender for Endpoint – Network | `DeviceNetworkEvents` | Suspicious outbound traffic |
|  02      | Network / Firewall Logs         | `CommonSecurityLog`   | Large data transfers        |
|  03      | Cloud Application Logs          | `CloudAppEvents`      | Cloud uploads               |
|  04      | DNS Telemetry                   | `DnsEvents`           | DNS tunneling               |
|  05      | Defender for Endpoint – Process | `DeviceProcessEvents` | Exfiltration tools          |

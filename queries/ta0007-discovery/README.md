# TA0007 – Discovery

## Overview

**Discovery** represents techniques adversaries use to **gain knowledge about the environment** after gaining access. This includes identifying users, systems, network topology, security controls, and trust relationships.

In **KQL Hunter**, Discovery hunting focuses on detecting **unusual enumeration commands, system and network reconnaissance, directory queries, and cloud environment discovery activity** using endpoint, identity, and network telemetry.

---

## Why Discovery Matters

- Discovery usually follows **initial access or execution**
- Enumeration activity reveals attacker intent
- Excessive discovery indicates **active threat progression**
- Early detection can prevent lateral movement
- Primary Discovery Techniques (MITRE ATT&CK)

---

## Top Data Sources for Discovery Hunting

Discovery detection relies on spotting enumeration behavior patterns:

| Priority   | Data Source                     | Table Name            | Use Case                 |
|------------| ------------------------------- | --------------------- | ------------------------ |
| ⭐ 1      | Defender for Endpoint – Process | `DeviceProcessEvents` | Enumeration commands     |
| ⭐ 2      | Defender for Endpoint – Network | `DeviceNetworkEvents` | Network scanning         |
| ⭐ 3      | Windows Security Logs           | `SecurityEvent`       | Account & system queries |
| ⭐ 4      | Azure AD Sign-in Logs           | `SigninLogs`          | Cloud discovery          |
| ⭐ 5      | Azure AD Audit Logs             | `AuditLogs`           | Directory enumeration    |

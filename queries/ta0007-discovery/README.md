# TA0007 – Discovery

## Overview

**[Discovery](https://attack.mitre.org/tactics/TA0007/)** represents techniques adversaries use to **gain knowledge about the environment** after gaining access. This includes identifying users, systems, network topology, security controls, and trust relationships.

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
|    01      | Defender for Endpoint – Process | `DeviceProcessEvents` | Enumeration commands     |
|    02      | Defender for Endpoint – Network | `DeviceProcessEvents` | Network scanning         |
|    03      | Windows Security Logs           | `SecurityEvent`       | Account & system queries |

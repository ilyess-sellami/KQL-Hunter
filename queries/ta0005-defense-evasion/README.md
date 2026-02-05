# TA0005 – Defense Evasion

## Overview

**[Defense Evasion](https://attack.mitre.org/tactics/TA0005/)** represents techniques adversaries use to **avoid detection, bypass security controls, and hide malicious activity**. Once attackers gain execution or elevated privileges, evasion techniques are often used to remain undetected while continuing operations.

In **KQL Hunter**, Defense Evasion hunting focuses on identifying **security control tampering, log clearing, obfuscation, masquerading, and abuse of trusted system utilities** across endpoint, identity, and network telemetry.

---

## Why Defense Evasion Matters

- Evasion enables **long-term stealth**
- Security control tampering often precedes ransomware
- Many evasion actions are **high-impact and rare**
- Detecting evasion indicates **active adversary presence**

---

## Top Data Sources for Defense Evasion Hunting

Defense evasion detection relies on spotting changes that weaken security posture:

| Priority | Data Source                        | Table Name              | Use Case                    |
| -------- | ---------------------------------- | ----------------------- | --------------------------- |
|   01     | Defender for Endpoint – Process    | `DeviceProcessEvents`   | Security tool tampering     |
|   02     | Windows Security Logs              | `SecurityEvent`         | Log clearing, audit disable |
|   03     | Defender for Endpoint – Registry   | `DeviceRegistryEvents`  | AV / Defender changes       |
|   04     | Defender for Endpoint – File       | `DeviceFileEvents`      | Hidden / renamed files      |
|   05     | Defender for Endpoint – Image Load | `DeviceImageLoadEvents` | LOLBin abuse                |

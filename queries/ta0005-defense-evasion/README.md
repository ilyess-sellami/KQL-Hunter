# TA0005 – Defense Evasion

## Overview

**Defense Evasion** represents techniques adversaries use to **avoid detection, bypass security controls, and hide malicious activity**. Once attackers gain execution or elevated privileges, evasion techniques are often used to remain undetected while continuing operations.

In **KQL Hunter**, Defense Evasion hunting focuses on identifying **security control tampering, log clearing, obfuscation, masquerading, and abuse of trusted system utilities** across endpoint, identity, and network telemetry.

---

## Why Defense Evasion Matters

- Evasion enables **long-term stealth**
- Security control tampering often precedes ransomware
- Many evasion actions are **high-impact and rare**
- Detecting evasion indicates **active adversary presence**

---

## Primary Defense Evasion Techniques (MITRE ATT&CK)

Common techniques covered in this section include:

- **T1562 – Impair Defenses**
- **T1070 – Indicator Removal on Host**
- **T1027 – Obfuscated or Encrypted Files/Information**
- **T1036 – Masquerading**
- **T1218 – Signed Binary Proxy Execution (LOLBins)**

Each query is **mapped directly to a MITRE Defense Evasion technique**.

---

## Top Data Sources for Defense Evasion Hunting

Defense evasion detection relies on spotting changes that weaken security posture:

| Priority | Data Source                        | Table Name              | Use Case                    |
| -------- | ---------------------------------- | ----------------------- | --------------------------- |
| ⭐ 1      | Defender for Endpoint – Process    | `DeviceProcessEvents`   | Security tool tampering     |
| ⭐ 2      | Windows Security Logs              | `SecurityEvent`         | Log clearing, audit disable |
| ⭐ 3      | Defender for Endpoint – Registry   | `DeviceRegistryEvents`  | AV / Defender changes       |
| ⭐ 4      | Defender for Endpoint – File       | `DeviceFileEvents`      | Hidden / renamed files      |
| ⭐ 5      | Defender for Endpoint – Image Load | `DeviceImageLoadEvents` | LOLBin abuse                |

# TA0006 – Credential Access

## Overview

Credential Access represents techniques adversaries use to **steal, dump, or abuse credentials** such as passwords, hashes, tokens, and authentication material. Successful credential access enables lateral movement, privilege escalation, and long‑term compromise.

In KQL Hunter, Credential Access hunting focuses on detecting **credential dumping, LSASS access, suspicious authentication behavior, token abuse, and access to sensitive credential stores** across endpoints and identity telemetry.

---

## Why Credential Access Matters

- Credentials enable **full environment takeover**
- Credential theft often leads to **lateral movement**
- Many techniques execute **quickly and quietly**
- Early detection prevents domain‑wide compromise

---

## Primary Credential Access Techniques (MITRE ATT&CK)

Common techniques covered in this section include:

- **T1003 – OS Credential Dumping**
- **T1555 – Credentials from Password Stores**
- **T1110 – Brute Force / Password Spraying**
- **T1550 – Use of Alternate Authentication Material**
- **T1621 – Multi-Factor Authentication Request Generation**

Each query is **mapped directly to a MITRE Credential Access technique**.

---

## Top Data Sources for Credential Access Hunting

Credential access detection requires endpoint visibility and identity context:

| Priority | Data Source                      | Table Name             | Use Case                        |
| -------- | -------------------------------- | ---------------------- | ------------------------------- |
| ⭐ 1      | Defender for Endpoint – Process  | `DeviceProcessEvents`  | LSASS dumping, credential tools |
| ⭐ 2      | Windows Security Logs            | `SecurityEvent`        | Credential usage and abuse      |
| ⭐ 3      | Azure AD Sign-in Logs            | `SigninLogs`           | Password spraying, MFA abuse    |
| ⭐ 4      | Defender for Endpoint – File     | `DeviceFileEvents`     | Credential files and dumps      |
| ⭐ 5      | Defender for Endpoint – Registry | `DeviceRegistryEvents` | Credential storage access       |

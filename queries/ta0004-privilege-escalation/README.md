# TA0004 – Privilege Escalation

## Overview

**Privilege Escalation** represents techniques adversaries use to **gain higher-level permissions** within a system or environment. After initial access or execution, attackers attempt to elevate privileges to gain administrative or system-level control.

In KQL Hunter, Privilege Escalation hunting focuses on detecting **abnormal privilege assignments, exploitation attempts, token abuse, UAC bypasses, and suspicious administrative actions** across endpoints and identity platforms.

---

## Why Privilege Escalation Matters

- Elevated privileges enable **full environment compromise**
- Many escalation techniques are **stealthy** and **short-lived**
- Admin-level access allows credential dumping and persistence
- Detecting escalation early limits attack progression

---

## Primary Privilege Escalation Techniques (MITRE ATT&CK)

Common techniques covered in this section include:

- **T1068 – Exploitation for Privilege Escalation**
- **T1548 – Abuse Elevation Control Mechanism**
- **T1134 – Access Token Manipulation**
- **T1078 – Valid Accounts (Privilege Abuse)**
- **T1055 – Process Injection**

Each query is **mapped directly to the appropriate MITRE technique**.

---

## Top Data Sources for Privilege Escalation Hunting

Privilege escalation detection relies on identity changes, process behavior, and security events:

| Priority | Data Source                        | Table Name              | Use Case                     |
| -------- | ---------------------------------- | ----------------------- | ---------------------------- |
| ⭐ 1      | Windows Security Logs              | `SecurityEvent`         | Admin logons, token usage    |
| ⭐ 2      | Defender for Endpoint – Process    | `DeviceProcessEvents`   | Exploit & injection activity |
| ⭐ 3      | Azure AD Audit Logs                | `AuditLogs`             | Role assignments             |
| ⭐ 4      | Defender for Endpoint – Registry   | `DeviceRegistryEvents`  | UAC bypass                   |
| ⭐ 5      | Defender for Endpoint – Image Load | `DeviceImageLoadEvents` | Injection indicators         |

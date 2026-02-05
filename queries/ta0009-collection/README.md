# TA0009 – Collection

## Overview

**[Collection](https://attack.mitre.org/tactics/TA0009/)** represents techniques adversaries use to **gather data of interest** from compromised systems and environments. After lateral movement, attackers search for sensitive files, emails, databases, and other valuable information before exfiltration.

In **KQL Hunter**, Collection hunting focuses on detecting **abnormal file access, large‑scale data reads, mailbox access, clipboard activity, and data aggregation behavior** across endpoint, email, and cloud telemetry.

---

## Why Collection Matters

- Indicates attacker is **preparing for exfiltration**
- Often targets **high‑value data**
- Collection activity can be **slow and stealthy**
- Detecting it limits data loss impact

---

## Top Data Sources for Collection Hunting

Collection detection relies on monitoring data access patterns:

| Priority | Data Source                     | Table Name            | Use Case              |
| -------- | ------------------------------- | --------------------- | --------------------- |
|  01      | Defender for Endpoint – File    | `DeviceFileEvents`    | Sensitive file access |
|  02      | Defender for Endpoint – Process | `DeviceProcessEvents` | Data harvesting tools |
|  03      | Defender for Office 365         | `EmailEvents`         | Mailbox access        |
|  04      | Cloud Application Logs          | `CloudAppEvents`      | Cloud data access     |
|  05      | Windows Security Logs           | `SecurityEvent`       | File share access     |
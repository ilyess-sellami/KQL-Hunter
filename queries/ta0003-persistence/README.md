# TA0003 – Persistence

## Overview

**Persistence** represents the techniques adversaries use to **maintain long-term access** to systems across reboots, logoffs, or credential changes. Once persistence is established, attackers can return at will and continue their operations stealthily.

In **KQL Hunter**, Persistence hunting focuses on detecting **abnormal startup mechanisms, registry modifications, scheduled tasks, service creation, and cloud configuration changes** that indicate an attacker is embedding themselves in the environment.

---

## Why Persistence Matters

- Persistence enables **long-term compromise**
- Many persistence techniques are **low-noise**
- Legitimate system features are commonly abused
- Early detection limits attacker dwell time

---

## Top Data Sources for Persistence Hunting

Persistence detection relies on changes over time rather than single events. These data sources provide the strongest signals:

| Priority | Data Source                      | Table Name             | Use Case                  |
| -------- | -------------------------------- | ---------------------- | ------------------------- |
| ⭐ 1      | Defender for Endpoint – Registry | `DeviceRegistryEvents` | Run keys, autoruns        |
| ⭐ 2      | Windows Security Logs            | `SecurityEvent`        | Scheduled tasks, services |
| ⭐ 3      | Azure AD Audit Logs              | `AuditLogs`            | Account & role changes    |
| ⭐ 4      | Defender for Endpoint – Process  | `DeviceProcessEvents`  | Persistence execution     |
| ⭐ 5      | Defender for Endpoint – File     | `DeviceFileEvents`     | Startup files             |

# TA0002 – Execution

## Overview

**Execution** represents the techniques adversaries use to **run malicious code** on a target system. After gaining access, attackers must execute commands, scripts, or binaries to continue their operations.

In **KQL Hunter**, Execution hunting focuses on identifying **suspicious process creation, script execution, abuse of legitimate tools (LOLBins), and abnormal command-line behavior** using endpoint and system telemetry.

---

## Why Execution Matters

- Execution is required for **every attack stage**
- Many attacks use **built-in system tools** to evade detection
- Abnormal command lines often reveal malicious intent
- Strong execution visibility enables **early threat disruption**

---

## Top Data Sources for Execution Hunting

Execution detection relies heavily on **endpoint telemetry**. The following data sources provide the strongest signals:

| Priority | Data Source                        | Table Name              | Use Case                               |
| -------- | ---------------------------------- | ----------------------- | -------------------------------------- |
| ⭐ 1      | Defender for Endpoint – Process    | `DeviceProcessEvents`   | Process creation & command lines       |
| ⭐ 2      | Windows Security Logs              | `SecurityEvent`         | Process creation (4688)                |
| ⭐ 3      | Defender for Endpoint – File       | `DeviceFileEvents`      | Script & binary execution              |
| ⭐ 4      | Defender for Endpoint – Image Load | `DeviceImageLoadEvents` | DLL & sideloading                      |
| ⭐ 5      | Defender for Endpoint – Network    | `DeviceNetworkEvents`   | Execution followed by network activity |

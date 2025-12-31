# KQL-Hunter

---

## Overview

**KQL Hunter** is an open-source repository of **Kusto Query Language (KQL) hunting queries** for **Microsoft Sentinel**, enriched with **MITRE ATT&CK mappings**. It provides a curated set of ready-to-use hunting queries, organized by domain (Endpoints, Network, Cloud, etc.) and mapped to MITRE ATT&CK techniques.

Whether you are a security analyst, cyber enthusiast, or Purple Team practitioner, KQL Hunter helps you **detect threats**, **practice detection scenarios**, **build SOC use-cases**, and **learn threat hunting** with a structured, practical approach aligned to real-world attacks.

---

## Introducing KQL

![KQL](docs/KQL.png)

**[KQL (Kusto Query Language)](https://learn.microsoft.com/en-us/kusto/query/?view=microsoft-fabric)** is the query language for **Azure Log Analytics** and **Microsoft Sentinel**. It allows you to efficiently search and analyze structured log data for insights and threat hunting.  

**Example KQL Query:**
```kql
SecurityEvent
| where EventID == 4625
| summarize count() by Account, bin(TimeGenerated, 1h)
| order by count_
```

---

## Microsoft Sentinel

[Microsoft Sentinel](docs/Microsoft-Sentinel.png)

**Microsoft Sentinel** is a **cloud-native SIEM/SOAR** that **uses KQL to analyze logs** across your environment.

With KQL Hunter, you can:

- Detect suspicious behavior
- Build correlation rules
- Map queries to MITRE ATT&CK tactics
- Share and collaborate on hunting techniques


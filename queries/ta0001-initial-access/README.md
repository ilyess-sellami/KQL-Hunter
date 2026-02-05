# TA0001 – Initial Access

## Overview

**Initial Access** represents the techniques adversaries use to gain their **first foothold** into an environment. This is one of the **most critical phases to detect**, as successful Initial Access often leads to privilege escalation, lateral movement, and full domain compromise.

In KQL Hunter, Initial Access hunting focuses on detecting **credential abuse, phishing-driven access, exposed services, and abnormal external authentication patterns** using identity, endpoint, and network telemetry from Microsoft Sentinel.

---

## Why Initial Access Matters

- Most breaches begin with **stolen credentials or phishing**
- Identity-based attacks are increasing across **cloud and hybrid environments**
- Early detection significantly reduces **blast radius and recovery time**
- Strong Initial Access coverage improves overall **SOC detection maturity**

---

## Top Data Sources for Initial Access Hunting

The following data sources provide the highest signal for detecting Initial Access activity in Microsoft Sentinel:

| Priority | Data Source                         | Table Name            | Primary Use Case                          |
| -------- | ----------------------------------- | --------------------- | ----------------------------------------- |
| ⭐ 1      | **Windows Security Logs**           | `SecurityEvent`       | Password spraying, brute force, RDP abuse |
| ⭐ 2      | **Azure AD Sign-in Logs**           | `SigninLogs`          | Cloud identity abuse, MFA anomalies       |
| ⭐ 3      | **Network / Firewall Logs**         | `CommonSecurityLog`   | External access to exposed services       |
| ⭐ 4      | **Defender for Endpoint (Process)** | `DeviceProcessEvents` | Malicious execution after access          |
| ⭐ 5      | **Defender for Endpoint (Network)** | `DeviceNetworkEvents` | Suspicious inbound/outbound connections   |
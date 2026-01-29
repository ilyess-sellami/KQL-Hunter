# TA0001 – Initial Access

## Overview

**Initial Access** represents the techniques adversaries use to gain their **first foothold** into an environment. This stage is one of the **most critical phases to detect**, as early detection can prevent lateral movement, credential theft, and full compromise.

In **KQL Hunter**, Initial Access queries focus on identifying **suspicious authentication activity, phishing attempts, exposed services, and abnormal external access patterns** across cloud, endpoint, and network telemetry.

---

## Why Initial Access Matters

- Most breaches begin with **stolen credentials or phishing**
- Cloud and identity-based attacks are increasing rapidly
- Early detection drastically reduces incident impact
- Strong Initial Access hunting improves **SOC maturity**

---

## Primary Initial Access Techniques (MITRE ATT&CK)

Some of the most common techniques covered in this section:

- **T1078 – Valid Accounts**
- **T1110 – Brute Force / Password Spraying**
- **T1566 – Phishing**
- **T1190 – Exploit Public-Facing Application**
- **T1133 – External Remote Services**

Each query in this folder is **mapped directly to a MITRE technique**.

---

## Top Data Sources for Initial Access Hunting

The following data sources provide the highest signal for detecting Initial Access activity in Microsoft Sentinel:

| Priority | Data Source                | Table Name            | Use Case                              |
| -------- | -------------------------- | --------------------- | ------------------------------------- |
| ⭐ 1      | Azure AD Sign-in Logs      | `SigninLogs`          | Suspicious logins, MFA abuse, new IPs |
| ⭐ 2      | Defender for Office 365    | `EmailEvents`         | Phishing-based access                 |
| ⭐ 3      | Windows Security Logs      | `SecurityEvent`       | On-prem brute force                   |
| ⭐ 4      | Network / Firewall Logs    | `CommonSecurityLog`   | VPN & perimeter access                |
| ⭐ 5      | Defender Network Telemetry | `DeviceNetworkEvents` | Suspicious inbound connections        |

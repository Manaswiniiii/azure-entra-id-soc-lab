# Azure Entra ID SOC Lab with Microsoft Sentinel

This project demonstrates a hands-on SOC lab built in Microsoft Azure using Microsoft Entra ID and Microsoft Sentinel to simulate real-world IAM threat detection, log analysis, and incident response.

The lab was created using a custom Entra ID tenant to overcome university tenant restrictions and gain full control over identity logs, user behavior, and security monitoring.

---

## Lab Architecture

- Custom Microsoft Entra ID tenant
- Multiple test users created for login simulation
- Log Analytics Workspace connected to Microsoft Sentinel
- Azure AD / Entra ID diagnostic logs streamed to Sentinel
- KQL-based threat hunting and alert rule creation

---

## What Was Implemented

### 1. Created a Dedicated Entra ID Tenant
- New tenant created with onmicrosoft.com domain
- Internal users provisioned for login activity simulation

### 2. Microsoft Sentinel Integration
- Log Analytics Workspace connected to Sentinel
- Entra ID Sign-in logs and Audit logs ingested

### 3. IAM Log Monitoring with KQL
Wrote multiple KQL queries to detect:

- Failed login attempts (brute force patterns)
- Logins from unusual locations
- Privilege misuse and role changes
- Suspicious sign-in patterns
- Account lockouts
- First-time login detection

### 4. Custom Alert Rules
- Alerts created from KQL queries
- Incidents generated inside Sentinel

### 5. Incident Investigation
- Investigated incidents using:
  - SigninLogs
  - AuditLogs
  - User behavior patterns

---

## Sample KQL Queries Used

```kql
SigninLogs
| where ResultType != 0
| summarize FailedAttempts = count() by UserPrincipalName, IPAddress
| sort by FailedAttempts desc


Skills Demonstrated
	•	Microsoft Sentinel (SIEM)
	•	Microsoft Entra ID (IAM)
	•	KQL (Kusto Query Language)
	•	Log Analysis & Threat Hunting
	•	SOC Alert Rule Creation
	•	Incident Investigation



# SOC Analyst L1 – Daily Report

**Date:** 2025-09-07  
**Shift:** Morning (08:00 – 16:00 UTC)  
**Analyst:** Posaram  

---

## 1. Executive Summary
- Total alerts reviewed: **10**  
- Severity breakdown: 2 High, 3 Medium, 5 Low  
- Actions taken:  
  - 1 High alert escalated to L2  
  - 1 Medium alert closed as False Positive  
  - 8 alerts monitored and documented  

---

## 2. Alerts Reviewed

| Alert ID     | Severity | Host/User   | Description                          | Action Taken          |
|--------------|----------|-------------|--------------------------------------|-----------------------|
| SIEM-2025-001 | High     | WEB-SERVER1 | Suspicious outbound traffic to 45.33.21.11 | Escalated to L2 (Ticket: INC-101) |
| SIEM-2025-002 | Medium   | HR-PC       | AV detected suspicious.exe           | Closed as False Positive |
| SIEM-2025-003 | Medium   | user01      | Multiple failed logins               | User confirmed typo; monitored |
| SIEM-2025-004 | Low      | DB-SERVER1  | Single port scan detected            | Documented only |
| ...          | ...      | ...         | ...                                  | ... |

---

## 3. Detailed Investigation

### Alert: SIEM-2025-001 (Escalated)
- **Description:** Outbound connection from WEB-SERVER1 to unknown IP 45.33.21.11  
- **Evidence Collected:**  
  - SIEM logs showed >1000 connections in 10 mins.  
  - Endpoint check: active nginx process making connection.  
- **Action:**  
  - Blocked IP on firewall (temporary).  
  - Escalated to L2 with evidence (Ticket: INC-101).  
- **Status:** Pending L2 investigation.  

---

### Alert: SIEM-2025-002 (False Positive)
- **Description:** Antivirus flagged `suspicious.exe` on HR-PC.  
- **Evidence:**  
  - File hash checked on VirusTotal → Clean.  
  - Vendor confirmed false positive after signature update.  
- **Action:** Closed ticket.  
- **Status:** Resolved.  

---

## 4. End of Shift Notes
- Pending escalation: INC-101 (WEB-SERVER1 outbound traffic).  
- Next shift: Please monitor if any other servers connect to same IP range.  

---

## 5. Attachments
- SIEM queries used (Splunk/Elastic).  
- Firewall block confirmation screenshot.  
- Log extracts from endpoints.  

---

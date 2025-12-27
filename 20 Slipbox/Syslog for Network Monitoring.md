---
tags:
  - networking/monitoring
  - security/logging
  - devops/observability
created: 2025-12-28
check: verified
---

# Syslog for Network Monitoring

**Definition:** A standardized protocol (UDP 514) for sending log and event messages from network devices to a central log server. It's crucial for troubleshooting, security, and compliance.

### Syslog Message Structure
A typical message: `<PRI> timestamp hostname tag: message`

| Component | Description | Example (from `router01 SSHD[12345]: Login successful...`) |
| :--- | :--- | :--- |
| **`<PRI>`** | Encoded priority (Facility x 8 + Severity) | `<189>` (Facility 23 `local7`, Severity 5 `Notice`) |
| **Timestamp** | Time of the event | `Jan 14 10:24:01` |
| **Hostname** | Source device name or IP | `router01` |
| **Tag** | Process or module generating the log | `SSHD[12345]` |
| **Message** | Description of the event | `Login successful from 192.168.1.100` |

### Severity Levels (0 = Most Critical, 7 = Least Critical)

| Level | Name | Description | Action Required |
| :--- | :--- | :--- | :--- |
| **0** | **Emergency** | System is unusable. | Immediate intervention (e.g., system crash). |
| **1** | **Alert** | Immediate action required. | Critical events (e.g., power supply failed). |
| **2** | **Critical** | Critical conditions. | Recoverable failure (e.g., primary link down). |
| **3** | **Error** | Non-critical error occurred. | Device still functions, but something failed (e.g., interface flapping). |
| **4** | **Warning** | Potential issue, may escalate. | Something abnormal, but not yet an error (e.g., high CPU usage). |
| **5** | **Notice** | Important event, not an error. | Normal but significant (e.g., user login/logout). |
| **6** | **Informational** | General operational message. | Routine info (e.g., interface up/down). |
| **7** | **Debug** | Debug-level messages. | Very verbose, used for deep troubleshooting. |

### Cisco Configuration Example
```cli
Router> enable
Router# configure terminal
Router(config)# logging trap warnings        // Send logs of 'warning' severity (level 4) and higher to the Syslog server
Router(config)# logging x.x.x.x              // The IP address of your Syslog server
Router(config)# service timestamps log datetime msec  // Add precise timestamps to logs
Router(config)# logging console informational  // Optional: send informational logs and higher to the console port
Router(config)# end
```

Syslog Receiver Tools
Tool Name	Platform	Features	Strengths
Kiwi Syslog	Windows	GUI-based, filtering (severity, host, text), alerting (sound, email).	Easy to install, free for basic use.
Graylog	Linux/Windows	Enterprise-grade log aggregation, dashboards, advanced search, real-time alerts.	Scalable, powerful for large environments.
Syslog-ng	Linux	High-performance log collector, advanced routing/filtering.	Flexible, efficient for complex setups.
TFTPD32	Windows	Lightweight, multi-function (Syslog, DHCP, TFTP server).	Simple, good for small labs.
Filtering and Analysis
Kiwi: Filter by Source IP, Severity, Message Text to quickly find events like "login failure" from a specific device.
Graylog: Build dashboards to visualize trends (e.g., "Top 5 most logged devices"). Create alerts for specific critical events (e.g., "Alert me if 'facility: local7 AND severity:3 AND source:switch-1' occurs").


Related:
[[Network Management Protocols]] (SNMP for status)
[[Firewalls and NGFW]] (Log analysis is crucial for security)

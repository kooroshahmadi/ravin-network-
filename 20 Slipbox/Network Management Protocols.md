---
tags:
  - networking/protocols
  - management
created: 2025-12-15
check: enriched
---

# Network Management Protocols

### 1. SNMP (Simple Network Management Protocol)
![[snmp.jpg]]
*   **Ports:** UDP 161 (Polling), UDP 162 (Traps/Alerts).
*   **Role:** Monitoring device health (CPU usage, bandwidth, uptime).
*   **Components:**
    *   **Manager:** The central dashboard.
    *   **Agent:** The software running on the router/switch.
    *   **Trap:** An emergency alert sent by the Agent to the Manager.

### 2. NTP (Network Time Protocol)
![[NTP.png]]*   **Port:** UDP 123.
*   **Role:** Synchronizing clocks.
*   **Importance:**
    *   **Log Analysis:** You can't correlate a hack if Router A says it's 2:00 PM and Router B says it's 4:00 AM.
    *   **Auth:** Kerberos (Windows Login) fails if time is off by >5 minutes.

### 3. DHCP (Dynamic Host Configuration Protocol)
![[DHCP packet format.webp]]
*   **Ports:** UDP 67 (Server), UDP 68 (Client).
*   **Role:** Assigning IP addresses automatically.
*   **The DORA Process:**
    1.  **D**iscover (Client yells "Help!")
    2.  **O**ffer (Server says "Here is an IP")
    3.  **R**equest (Client says "I'll take it")
    4.  **A**cknowledge (Server says "It's yours")
![[working of DHCP.webp]]
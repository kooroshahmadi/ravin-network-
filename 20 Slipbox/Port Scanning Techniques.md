---
tags:
  - security/tools
  - scanning
  - tcp-udp
created: 2025-12-28
check: enriched
---

# Port Scanning Techniques

Once a host is found, Nmap probes the ports (0-65535) to see what services are listening.

### The Three States
1.  **Open:** Application is listening and accepting connections. (Target).
2.  **Closed:** No application is listening, but the OS replied saying "Go away" (RST packet).
3.  **Filtered:** A **Firewall** dropped the packet. Nmap got no response at all.

### Common Scan Types

#### 1. TCP SYN Scan (`-sS`) - "Stealth Scan"
*   **Requires Root:** Yes.
*   **Behavior:** Sends SYN. Receives SYN-ACK. Sends **RST** (Reset) immediately.
*   **Why:** It never completes the "3-Way Handshake," so the server often doesn't log the connection. It is fast and quiet.

#### 2. TCP Connect Scan (`-sT`)
*   **Requires Root:** No (Default for non-admin users).
*   **Behavior:** Completes the full 3-Way Handshake (SYN -> SYN-ACK -> ACK).
*   **Why:** Slower and noisier (appears in server logs), but works on any machine.

#### 3. UDP Scan (`-sU`)
*   **Behavior:** Sends empty UDP packets to ports.
*   **Difficulty:** UDP is "connectionless," so it often doesn't reply. Nmap has to wait for a timeout.
*   **Result:** extremely **Slow**. Scanning all 65k UDP ports can take hours.

### Service Version Detection (`-sV`)
Instead of just saying "Port 80 is Open," Nmap talks to the port to figure out *exactly* what is running.
*   *Output:* `Port 80: Apache httpd 2.4.41 (Ubuntu)`
*   *Value:* Helps identify vulnerable software versions.
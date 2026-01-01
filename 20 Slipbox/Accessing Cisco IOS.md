---
tags:
  - cisco/cli
  - hardware
created: 2026-01-01
check: verified
---

# Accessing Cisco IOS

**IOS (Internetwork Operating System)** is the kernel that runs Cisco devices. It is stored in **Flash Memory**.

### Physical Access (Console)
Used for initial configuration when the device has no IP address.
*   **Cable:** Rollover Cable (Light Blue).
    *   *End A:* DB-9 (Serial) or USB-A (Computer side).
    *   *End B:* RJ-45 or Mini-USB (Router side).
*   **Terminal Settings (The "9600-8-N-1" Rule):**
    *   **Speed:** 9600 Baud.
    *   **Data Bits:** 8.
    *   **Parity:** None (No).
    *   **Stop Bits:** 1.
    *   **Flow Control:** None.

### Remote Access (Virtual Lines)
Used once the device has an IP.
*   **Telnet:** Port 23. Clear text. (Insecure).
*   **SSH:** Port 22. Encrypted. (Recommended).
*   **VTY Lines:** The virtual ports on the router that accept these connections (usually `line vty 0 4`).

### Help Features
*   `?`: Context-sensitive help. (e.g., `show ?` lists all show commands).
*   `TAB`: Autocomplete a command.
*   `Up Arrow`: Recall previous commands (History).

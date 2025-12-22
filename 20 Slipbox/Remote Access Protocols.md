---
tags:
  - networking/protocols
  - remote-access
created: 2025-12-15
check: verified
---

# Remote Access Protocols

Protocols used to control a remote computer.

### 1. Telnet (Telecommunication Network)
![[telnet.png]]
*   **Port:** TCP 23.
*   **Interface:** Command Line (CLI).
*   **Security:** ❌ **None.** Everything (including passwords) is Clear Text.
*   **Use:** Debugging ports, testing connections (Legacy).

### 2. SSH (Secure Shell)
![[SSH.png]]
*   **Port:** TCP 22.
*   **Interface:** Command Line (CLI).
*   **Security:** ✅ **High.** Uses Public/Private Key encryption.
*   **Features:** Replaces Telnet. Can also "Tunnel" other traffic (Port Forwarding).

### 3. RDP (Remote Desktop Protocol)
*   **Port:** TCP 3389.
*   **Interface:** Graphical User Interface (GUI).
*   **Owner:** Microsoft (Proprietary).
*   **Components:** RDS (Server) and RDC (Client).
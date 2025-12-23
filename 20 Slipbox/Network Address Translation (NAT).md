---
tags:
  - networking/addressing
  - security
created: 2025-12-23
check: enriched
---

# Network Address Translation (NAT)

**Role:** Allows private networks (LAN) to communicate over the public Internet by modifying IP headers.

### Types of NAT
1.  **Static NAT (SNAT):** One-to-One. (Server 192.168.1.5 always equals Public IP 8.8.8.8). Used for Web Servers.
2.  **Dynamic NAT:** Pool of IPs. First come, first served.
3.  **PAT (Port Address Translation):** One-to-Many. **"NAT Overload."**
    *   *Usage:* Your home router. All your devices (Phone, PC, TV) go out using **one** Public IP. The router uses **Port Numbers** to remember who asked for what.

### Terminology (Cisco Lingo)
*   **Inside Local:** The Private IP of your PC (192.168.1.10).
*   **Inside Global:** The Public IP your PC looks like to the world.
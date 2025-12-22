---
tags:
  - networking/hardware
  - layer3
  - routing
created: 2025-12-22
check: verified
---

# Routers

**Definition:** A Layer 3 device that connects **different** networks together (e.g., Your LAN to the Internet).

### Key Functions
1.  **Packet Forwarding:** Moves data based on **IP Address** (not MAC).
2.  **Broadcast Control:** Routers **do not** forward broadcast traffic. They contain the noise within the LAN.
3.  **Services:** Most modern routers also act as:
    *   **NAT:** Translating Private IPs to Public IPs.
    *   **DHCP Server:** Assigning IPs.
    *   **Gateway:** The exit point for the network.

> [!note] Multilayer Switch (Layer 3 Switch)
> A switch that can perform routing functions. It allows different VLANs to talk to each other without needing a dedicated router (Inter-VLAN Routing).
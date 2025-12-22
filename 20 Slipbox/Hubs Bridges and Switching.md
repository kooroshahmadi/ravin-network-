---
tags:
  - networking/hardware
  - layer2
created: 2025-12-22
check: verified
---

# Hubs, Bridges, and Switching

The evolution of connecting devices on a LAN.

### 1. Hub (Layer 1 - Dumb)
![[Hubs.jpg]]
*   **Behavior:** "Multi-port Repeater." If data comes in Port 1, it blasts it out Ports 2, 3, 4, and 5.
*   **Collision Domain:** Creates **1** single, large collision domain. If two people talk at once, data corrupts.
*   **Security:** Zero. Anyone can plug in a packet sniffer and see everyone's data.

### 2. Bridge (Layer 2 - Smarter)
![[Bridge.png]]
*   **Behavior:** Connects two network segments. It learns MAC addresses to decide if traffic needs to cross the bridge or stay on one side.
*   **Goal:** Reduces collision domains by splitting one big LAN into two.

### 3. Switch (Layer 2 - Intelligent)
![[Network-Switch-01-copy.webp]]
*   **Behavior:** Learns the MAC address of every device connected to it (ASIC hardware).
*   **Forwarding:** If Data comes in for Device A, the switch sends it *only* to Port A.
*   **Collision Domain:** **Micro-segmentation.** Every port is its own collision domain. (No collisions).

### Advanced Switch Features (Managed Switches)
*   **VLAN (Virtual LAN):** Logically separating departments (HR vs. Engineering) on the same physical switch for security.
*   **QoS (Quality of Service):** Giving priority to Voice/Video traffic so calls don't drop when someone downloads a file.
*   **Port Security:** Locking a port to a specific MAC address. If a hacker plugs in a rogue laptop, the port shuts down.
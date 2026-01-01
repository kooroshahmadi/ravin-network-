---
tags:
  - cisco/hardware
  - layer2
  - interfaces
created: 2026-01-01
check: verified
---

# Cisco Switch Hardware and Numbering

### Hardware Types
1.  **Fixed Configuration:** (e.g., Cisco 2960). You cannot add ports. If you need more ports, you buy a new switch.
2.  **Modular:** (e.g., Cisco 6500 or 9400). It has a "Chassis" (Metal box) and you slide "Line Cards" (Modules) into slots.
3.  **Stackable:** (e.g., Cisco 3750/9300). Fixed switches that can be connected with a special "Stack Cable" to act as one giant logic switch.

### Interface Naming Convention
Cisco uses a standard format: `InterfaceType Module/Port` (or `Stack/Module/Port`).

*   **FastEthernet (Fa):** 100 Mbps.
*   **GigabitEthernet (Gi):** 1 Gbps (1000 Mbps).
*   **TenGigabitEthernet (Te):** 10 Gbps.

**Example: `Gi 1/0/24`**
*   **Gi:** It is a Gigabit Port.
*   **1:** Switch #1 in the stack.
*   **0:** Module Slot 0 (Built-in).
*   **24:** The 24th port on that switch.

### Layer 2 vs. Layer 3 Switches
*   **L2 Switch:** Forwards frames based purely on **MAC Addresses**. (Traditional).
*   **L3 Switch (MLS):** Multi-Layer Switch. Can route packets based on **IP Addresses**. It is a "Router inside a Switch."
---
tags:
  - networking/tcp-ip
  - layer1
  - layer2
created: 2025-12-13
check: verified
---

# TCP/IP Network Interface Layer

**Definition:** The foundation of the TCP/IP suite. It handles the physical hardware and the framing rules to get data from one device to the **next directly connected device**.
*   *Combines OSI Layers 1 (Physical) & 2 (Data Link).*

### Core Functions
1.  **Physical Connection:** Converting digital bits into electrical voltage (copper), light (fiber), or radio waves (Wi-Fi).
2.  **Addressing:** Uses **MAC Addresses** to identify devices on the Local Area Network (LAN).
3.  **Error Detection:** Checks if the frame is corrupted (CRC checks).

### Key Components & Protocols
| Category | Examples |
| :--- | :--- |
| **Hardware** | Cables, **Switches**, NICs (Network Cards), Wi-Fi Antennas. |
| **Protocols** | **Ethernet** (802.3), **Wi-Fi** (802.11), **PPP** (Point-to-Point). |
| **Helper** | **ARP** (Address Resolution Protocol) - Maps IP addresses to MAC addresses. |

> [!important] Note on Routers
> **Routers** are *Internet Layer* devices because they read IP addresses. **Switches** are *Network Interface Layer* devices because they read MAC addresses.

```mermaid
graph LR
    PC[Computer] -- "Digital Data" --> NIC[NIC Card]
    NIC -- "Electrical Signals" --> Cable
    Cable -- "Frame" --> Switch
```

Related:
[[802.11 Wireless Standards]]
[[Topology Basics and Types]]
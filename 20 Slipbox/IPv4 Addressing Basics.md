---
tags:
  - networking/addressing
  - ipv4
created: 2025-12-25
check: verified
---

# IPv4 Addressing Basics

**Definition:** A 32-bit logical address used to identify a device on a Layer 3 network.
*   **Format:** Dotted Decimal (e.g., `192.168.1.1`).
*   **Structure:** Split into **Network ID** (Street Name) and **Host ID** (House Number).

### IP Classes (The Legacy System)
| Class | First Octet | Range | Default Subnet Mask | Usage |
| :--- | :--- | :--- | :--- | :--- |
| **A** | 0 - 126 | `1.0.0.0` - `126.x.x.x` | 255.0.0.0 (/8) | Massive Networks (ISPs) |
| **B** | 128 - 191 | `128.0.0.0` - `191.x.x.x` | 255.255.0.0 (/16) | Medium Networks |
| **C** | 192 - 223 | `192.0.0.0` - `223.x.x.x` | 255.255.255.0 (/24) | Small LANs |
| **D** | 224 - 239 | `224.0.0.0` - `239.x.x.x` | N/A | **Multicast** (Streaming) |
| **E** | 240 - 254 | `240.0.0.0` - `254.x.x.x` | N/A | **Experimental/R&D** |

### Special Address Ranges
1.  **Loopback (`127.0.0.0/8`):** Refers to "Myself" (`localhost`). Used for testing if the NIC driver is working.
2.  **APIPA (`169.254.x.x`):** "Automatic Private IP."
    *   If a computer asks for a DHCP address but gets no reply, it assigns itself an address in this range.
    *   *Limitation:* You can talk to local neighbors, but you **cannot** reach the internet.

### Private IP Ranges (RFC 1918)
These are not routable on the public internet.
*   **Class A:** `10.0.0.0` to `10.255.255.255`
*   **Class B:** `172.16.0.0` to `172.31.255.255` (Note: Ends at 31, not 255!)
*   **Class C:** `192.168.0.0` to `192.168.255.255`
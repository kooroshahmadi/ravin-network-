---
tags:
  - networking/tcp-ip
  - transport
created: 2025-12-14
check: verified
---

# TCP/IP Transport Layer

**Definition:** Defines the level of service and status of the connection used when transporting data. It creates a "Host-to-Host" logical connection.
*   *Maps directly to OSI Layer 4.*

### Core Functions
1.  **Reliability vs. Speed:** Decides whether to use **TCP** (guaranteed delivery) or **UDP** (fast transmission).
2.  **Flow Control:** Manages the rate of data transmission so the sender doesn't overwhelm the receiver (TCP only).
3.  **Port Addressing:** Uses **Port Numbers** (e.g., Port 80 for Web) to direct traffic to the specific software application running on the host.

### Key Protocols
| Protocol | Full Name | Type | Usage |
| :--- | :--- | :--- | :--- |
| **TCP** | Transmission Control Protocol | **Connection-Oriented** | Web (HTTP), Email, FTP. Guarantees delivery. |
| **UDP** | User Datagram Protocol | **Connection-less** | Streaming, VoIP, DNS lookups. No error correction. |

> [!note] Cross-Reference
> For a deep dive on the "3-Way Handshake" and "Windowing," see the generic OSI note: [[Transport Layer and TCP]].

```mermaid
graph LR
    Sender -- "Source Port: 49152" --> Network
    Network -- "Dest Port: 80" --> WebServer
```

**Related:**

- [[TCP-IP Internet Layer]] (The layer below)
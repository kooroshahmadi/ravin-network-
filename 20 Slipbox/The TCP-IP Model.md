---
tags:
  - networking/models
  - tcp-ip
  - definitions
created: 2025-12-13
check: verified
---

# The TCP/IP Model

**Definition:** The practical, real-world model used for the Internet (Dept of Defense Model). It condenses the theoretical 7 OSI layers into 4 (or sometimes 5) practical layers.
![[working of TCPIP model.webp]]
### OSI vs. TCP/IP Mapping

| OSI Layer | TCP/IP Layer (4-Layer Ver) | Function |
| :--- | :--- | :--- |
| Application (7) <br> Presentation (6) <br> Session (5) | **Application** | Services, Encoding, Dialog |
| Transport (4) | **Transport** | Reliability & Flow Control |
| Network (3) | **Internet** | IP Addressing & Routing |
| Data Link (2) <br> Physical (1) | **Network Interface** | Physical transmission & MAC framing |

![[Layer of TCPIP model.webp]]
### Goal
*   **Reliability:** ensuring data survives path failures.
*   **Routability:** moving data across different network types (Ethernet to Wi-Fi to Fiber).

```mermaid
graph TD
    subgraph OSI
    L7[7. Application]
    L6[6. Presentation]
    L5[5. Session]
    L4[4. Transport]
    L3[3. Network]
    L2[2. Data Link]
    L1[1. Physical]
    end

    subgraph "TCP/IP"
    T4[Application]
    T3[Transport]
    T2[Internet]
    T1[Network Interface]
    end

    L7 & L6 & L5 -.-> T4
    L4 -.-> T3
    L3 -.-> T2
    L2 & L1 -.-> T1
    
    style T2 fill:#f96,stroke:#333
    style T1 fill:#99ccff,stroke:#333
```

Related:
[[The OSI Model Framework]]
[[TCP-IP Internet Layer]]
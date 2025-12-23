---
tags:
  - networking/redundancy
  - protocols
created: 2025-12-23
check: verified
---

# High Availability (Gateway Redundancy)

What happens if your Default Gateway (Router) dies? The internet cuts out.
**First Hop Redundancy Protocols (FHRP)** create a "Virtual Router" so users never notice a failure.

### The Protocols
| Protocol | Full Name | Vendor | Features |
| :--- | :--- | :--- | :--- |
| **HSRP** | Hot Standby Router Protocol | **Cisco** | Active/Standby. One router works, one sleeps. |
| **VRRP** | Virtual Router Redundancy Protocol | **Open Standard** | Active/Standby. Works on any brand. |
| **GLBP** | Gateway Load Balancing Protocol | **Cisco** | Active/Active. **Both** routers work and share traffic. |

```mermaid
graph TD
    PC[Client PC]
    Switch
    
    subgraph "Virtual Router (192.168.1.1)"
    R1[Router A - Active]
    R2[Router B - Standby]
    end
    
    PC -- "Gateway: .1" --> Switch
    Switch --> R1
    R1 -. "Keepalive" .- R2
    
    style R1 fill:#99ff99
    style R2 fill:#ff9999
```


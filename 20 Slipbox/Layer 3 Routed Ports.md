---
tags:
  - cisco/switching
  - layer3
  - config
created: 2026-01-02
check: verified
---

# Layer 3 Routed Ports

**Context:** The instructor's note used `no switchport`. This command is unique to **Multilayer Switches (MLS)**.

### Switchport vs. Routed Port
1.  **Switchport (Layer 2):** Uses MAC addresses. Supports VLANs/Trunks.
    *   *Default behavior of most ports.*
2.  **Routed Port (Layer 3):** Acts exactly like a **Router Interface**. It has an IP address. It **does not** support VLANs.

### Configuration
This turns a switch port into a gateway.

```cli
Switch(config)# interface fa0/1
Switch(config-if)# no switchport        <-- Disable L2 Switching capabilities
Switch(config-if)# ip address 192.168.10.1 255.255.255.0
Switch(config-if)# no shutdown
```

[!important] Prerequisite  
You must enable routing on the switch globally first:  
Switch(config)# ip routing
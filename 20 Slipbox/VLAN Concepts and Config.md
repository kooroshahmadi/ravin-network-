---
tags:
  - cisco/vlan
  - switching
  - segmentation
created: 2026-01-02
check: enriched
---

# VLAN Concepts and Config

**Virtual LAN (VLAN):** A logical way to separate networks on the same physical switch.
*   **Goal:** Segmentation. Broadcasts from VLAN 10 *cannot* reach VLAN 20.
*   **Layer 2 Boundary:** Different VLANs = Different Subnets. To talk between them, you need a **Router** (or L3 Switch).

### VLAN ID Ranges
| Range | IDs | Usage |
| :--- | :--- | :--- |
| **Normal** | **1 - 1005** | Standard usage. Saved in `vlan.dat` (Flash). |
| **Reserved** | **1002 - 1005** | Legacy (Token Ring/FDDI). Cannot use or delete. |
| **Extended** | **1006 - 4094** | Advanced usage (ISPs). Saved in `running-config`. |

### Configuration (Access Ports)
An **Access Port** belongs to ONE VLAN. Used for end devices (PCs, Printers).

```cli
! Step 1: Create the VLAN
Switch(config)# vlan 10
Switch(config-vlan)# name HR

! Step 2: Assign a Port
Switch(config)# interface fa0/1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 10

! Tip: Assign Multiple Ports
Switch(config)# interface range fa0/2 - 5
Switch(config-if-range)# switchport access vlan 10
```

### Verification

- show vlan brief: Lists all VLANs and the ports assigned to them.
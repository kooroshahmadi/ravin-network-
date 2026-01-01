---
tags:
  - cisco/config
  - management
  - telnet
created: 2026-01-01
check: enriched
---

# Management Access (SVI and Telnet)

To manage a Layer 2 Switch remotely, you must give it an IP address. Since physical ports don't have IPs, we use a **SVI (Switch Virtual Interface)**.

### 1. Configuring the SVI (The "Management IP")
```cli
Switch(config)# interface vlan 1           <-- Enter the virtual interface
Switch(config-if)# ip address 192.168.1.10 255.255.255.0
Switch(config-if)# no shutdown             <-- Turn it on (SVI is down by default)
Switch(config)# ip default-gateway 192.168.1.1  <-- Required to reach switch from other subnets
```

2. Configuring Telnet (VTY Lines)
Telnet uses the VTY (Virtual Teletype) lines.
Prerequisite: The Switch MUST have an Enable Secret set, or Telnet will refuse connection.
code
Cli
Switch(config)# line vty 0 15              <-- Configure all 16 virtual lines
Switch(config-line)# password cisco
Switch(config-line)# login                 <-- Check for password
Switch(config-line)# transport input telnet <-- Allow Telnet (or 'ssh', or 'all')
3. Why login local is better
If you use login local on VTY lines, you can see which admin made changes.
code
Cli
Switch(config)# username bob secret bobpass
Switch(config)# line vty 0 15
Switch(config-line)# login local
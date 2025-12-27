---
tags:
  - networking/tools
  - windows
created: 2025-12-27
check: enriched
---

# Netsh and Telnet

### 1. Telnet (Port Tester)
While originally for remote control, we now use it to **test ports**.

| Command | Result | Meaning |
| :--- | :--- | :--- |
| `telnet google.com 80` | Blank screen / Connection Established | **Port is Open.** Firewall is allowing traffic. |
| `telnet google.com 80` | "Connecting..." -> Timeout | **Port is Closed/Blocked** by a firewall. |

### 2. Netsh (Network Shell)
The "Swiss Army Knife" for Windows networking.

| Command                    | Purpose                 | Scenario                                                                          |
| :------------------------- | :---------------------- | :-------------------------------------------------------------------------------- |
| `netsh int ip reset`       | **Reset TCP/IP Stack.** | "My internet is weird, and nothing else worked. Reinstall the drivers logically." |
| `netsh wlan show drivers`  | **Wi-Fi Info.**         | "Does my laptop support the latest Wi-Fi 6 standard?"                             |
| `netsh advfirewall set...` | **Firewall Config.**    | Configure Windows Firewall via command line.                                      |
| `netsh winsock reset`      | **Reset Sockets.**      | Fixes issues where malware hijacked the network adapter.                          |
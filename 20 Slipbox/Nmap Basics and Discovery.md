---
tags:
  - security/tools
  - reconnaissance
  - nmap
created: 2025-12-28
check: verified
---

# Nmap Basics and Discovery

**Definition:** Nmap (Network Mapper) is an open-source tool used for network discovery and security auditing.
*   **Goal:** To create a "Map" of the network (Topology, Active Hosts, Open Ports).

### Phase 1: Host Discovery (The "Ping Sweep")
Before scanning ports, Nmap tries to find which IP addresses are actually alive.
*   **Mechanism:** Sends ICMP Echo Requests (Pings) to a range of IPs.
*   **Result:**
    *   *Reply:* Host is active.
    *   *No Reply:* Host is down OR a **Firewall** is blocking ICMP.

### Key Discovery Flags
| Flag | Function | Usage Scenario |
| :--- | :--- | :--- |
| `-sn` | **Ping Scan Only.** No port scan. | "Who is alive on 192.168.1.0/24?" |
| `-Pn` | **No Ping.** Treat all hosts as Online. | "I know the server is up, but it blocks ping. Scan the ports anyway." |
| `-PE` | Uses ICMP Echo (Standard Ping). | Standard discovery. |

> [!tip] Root Privileges
> Running Nmap as `root` (Linux) or Administrator (Windows) allows it to use **Raw Sockets**. This lets Nmap craft custom packets (like ARP pings) that are much faster and more accurate than standard OS calls.



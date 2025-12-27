---
tags:
  - networking/tools
  - advanced
  - linux
created: 2025-12-27
check: enriched
---

# Advanced Network Tools

### 1. IPTables (Linux Firewall)
The built-in kernel firewall for Linux.
*   **Concepts:** Uses "Chains" (Input, Output, Forward).

| Command | Meaning | Purpose |
| :--- | :--- | :--- |
| `iptables -L` | **List.** Show all current rules. | "Why can't I SSH into this box?" |
| `iptables -A INPUT -p tcp --dport 80 -j ACCEPT` | **Append.** Add a rule to allow Port 80 (Web). | "Open the firewall for a web server." |
| `iptables -D` | **Delete.** Remove a rule. | "Oops, I blocked myself." |
| `iptables -F` | **Flush.** Delete **ALL** rules. | "Reset everything to default." |

### 2. TCPDump (Packet Analyzer)
A command-line version of Wireshark. Captures raw packets.

| Command | Purpose |
| :--- | :--- |
| `tcpdump -i eth0` | Listen on interface "eth0". |
| `tcpdump port 80` | Only capture web traffic. |
| `tcpdump host 192.168.1.5` | Only capture traffic to/from one specific PC. |
| `tcpdump -w capture.pcap` | Write output to a file (to open in Wireshark later). |

### 3. Route Command
Manages the "Map" the computer uses to decide where to send packets.

| Command (Windows)                               | Purpose                                                        |
| :---------------------------------------------- | :------------------------------------------------------------- |
| `route print`                                   | View the table.                                                |
| `route add 10.0.0.0 mask 255.0.0.0 192.168.1.1` | Manually tell the PC "To get to 10.x, go through 192.168.1.1". |
| `route delete 0.0.0.0`                          | Delete the default gateway (Breaks internet).                  |

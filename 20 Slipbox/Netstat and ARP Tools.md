---
tags:
  - networking/tools
  - security
created: 2025-12-27
check: verified
---

# Netstat and ARP Tools

### 1. NETSTAT (Network Statistics)
Shows active connections (Who is talking to whom?).

| Flag | Description | Troubleshooting Usage |
| :--- | :--- | :--- |
| `netstat -a` | **All.** Shows all active connections and listening ports. | "Is my Web Server actually listening on Port 80?" |
| `netstat -n` | **Numerical.** Don't resolve names (Show `8.8.8.8` instead of `google.com`). | Faster output; reveals true IPs. |
| `netstat -b` | **Binary.** Shows the *program* name (e.g., `chrome.exe`) creating the connection. | **Malware Hunting:** "Why is `unknown.exe` talking to Russia?" |
| `netstat -r` | **Route.** Shows the Routing Table. | Same as the `route print` command. |

### 2. ARP (Address Resolution Protocol)
Manages the IP-to-MAC mapping cache.

| Command    | Purpose                                       | Troubleshooting Usage                                                 |
| :--------- | :-------------------------------------------- | :-------------------------------------------------------------------- |
| `arp -a`   | **View Cache.** Lists all known IP/MAC pairs. | "I can ping the server, but what is its MAC address?"                 |
| `arp -d *` | **Delete Cache.** Clears the table.           | Force the computer to re-learn MACs (useful if you swapped a router). |
| `arp -s`   | **Static Map.** Manually link an IP to a MAC. | Prevents ARP Spoofing (rarely used manually).                         |
---
tags:
  - networking/tools
  - troubleshooting
  - icmp
created: 2025-12-27
check: verified
---

# PING Tool

**Definition:** The most basic connectivity test. It uses **ICMP Echo Request** packets to ask a host "Are you there?" and measures the **Round Trip Time (RTT)**.

### Common Error Messages & Troubleshooting

| Message | Meaning | Likely Cause | Solution |
| :--- | :--- | :--- | :--- |
| **Reply from x.x.x.x** | Success! | Everything is working. | N/A |
| **Request Timed Out** | No reply received within the time limit. | 1. The Host is offline.<br>2. A **Firewall** is blocking ICMP.<br>3. Packet loss on the wire. | Check physical cables. Check Firewall logs. |
| **Destination Host Unreachable** | Your computer doesn't know *how* to get there. | 1. **Default Gateway** is missing or wrong.<br>2. Local routing table issue. | Check `ipconfig` for Gateway. |
| **TTL Expired in Transit** | The packet died before reaching the target. | **Routing Loop.** The packet is bouncing back and forth between two routers forever. | Run `traceroute` to find the loop. |
| **General Failure** | Your NIC failed to send the packet. | Your own Network Card / Driver is broken or disabled. | Re-enable NIC or update drivers. |

> [!tip] Continuous Ping
> Use `ping -t <IP>` (Windows) to ping forever. Useful for wiggling a loose cable to see if the connection drops.


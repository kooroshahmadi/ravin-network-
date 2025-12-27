---
tags:
  - networking/tools
  - troubleshooting
  - routing
created: 2025-12-27
check: enriched
---

# TRACEROUTE Tool

**Definition:** Traces the path packets take to a destination by manipulating the **TTL (Time To Live)** field.
*   **Windows Command:** `tracert` (Uses ICMP).
*   **Linux/Unix Command:** `traceroute` (Uses UDP).

### Interpreting Output & Errors

| Output Symbol | Meaning               | Likely Cause                                                                                                                                            | Solution                                                                                                                  |
| :------------ | :-------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------ |
| **10.0.0.1**  | Success (Router IP)   | You reached a router (Hop).                                                                                                                             | N/A                                                                                                                       |
| `* * *`       | **Request Timed Out** | 1. **Firewall Drop:** The router is configured to drop "useless" ICMP traffic (common security practice).<br>2. **Packet Loss:** The link is congested. | If the trace continues *after* the `*`, it's just a firewall (Ignorable). If it stops completely, that's the break point. |
| `!N`          | **Net Unreachable**   | The router knows the Network doesn't exist.                                                                                                             | Routing table error on that specific router.                                                                              |
| `!H`          | **Host Unreachable**  | The router knows the IP is offline/invalid.                                                                                                             | The target is down.                                                                                                       |
| `!X`          | **Admin Prohibited**  | **Firewall Block.** The router explicitly blocked you.                                                                                                  | Check ACLs (Access Control Lists).                                                                                        |
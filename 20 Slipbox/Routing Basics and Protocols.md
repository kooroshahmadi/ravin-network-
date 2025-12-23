---
tags:
  - networking/routing
  - protocols
created: 2025-12-23
check: enriched
---

# Routing Basics and Protocols

**Routing** is the process of selecting the best path for traffic.

### 1. Static vs. Dynamic
*   **Static:** Manual entry (`ip route 10.0.0.0...`). Simple, secure, but doesn't adapt to failures.
*   **Dynamic:** Routers talk to each other. If a cable breaks, they automatically recalculate the route.

### 2. Dynamic Protocols Comparison
They speak different languages to share maps.

| Protocol | Type | Metric (How it chooses) | Speed | Notes |
| :--- | :--- | :--- | :--- | :--- |
| **RIP** | Distance Vector | **Hop Count** (Max 15) | Slow | Old, good for tiny networks only. |
| **EIGRP** | Hybrid | **Composite** (Bandwidth + Delay) | Fast | Cisco proprietary (mostly). very smart. |
| **OSPF** | Link State | **Cost** (Link Speed) | Fast | Industry standard for Enterprise. Maps the whole network. |
| **BGP** | Path Vector | **Path/Policies** | Slow | Runs the **Internet**. Connects ISPs. |

### 3. Administrative Distance (AD)
"Who do I trust more?" Lower number = Higher trust.
*   **Connected Interface:** 0 (Most trusted)
*   **Static Route:** 1
*   **EIGRP:** 90
*   **OSPF:** 110
*   **RIP:** 120
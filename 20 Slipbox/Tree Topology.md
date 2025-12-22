---
tags:
  - networking/topology
  - hierarchical
created: 2025-12-10
check: verified
---

# Tree Topology

**Definition:** A hierarchical structure often described as a "Star of Stars." It connects multiple Star networks via a main backbone cable to a Root Node (Central Hub).
![[tree_topology.webp]]
### Structure & Data Flow
*   **Hierarchy:** Data flows from Top (Root) -> Secondary Hub -> Device.
*   **The "Repeater" Effect:** Because it uses active hubs/switches at each node, the signal is regenerated, allowing the network to cover longer distances than a standard Star or Bus.
*   **Protocols:** Often used with **DHCP** and automatic configuration (SAC) because the hierarchy makes it easy to segment the network into branches (subnets).

### Pros & Cons
| Feature | Details |
| :--- | :--- |
| **Scalability** | ✅ Excellent. You can add new "branches" (Secondary Hubs) without disturbing the root. |
| **Signal Range** | ✅ Increases the distance a signal can travel (due to regeneration). |
| **Fault Tolerance** | ⚠️ **Partial.** If a *Device* fails, it's fine. If a *Secondary Hub* fails, that branch dies. |
| **Root Failure** | ❌ **Critical.** If the Central Root hub fails, the entire network crashes (Non-robust). |
| **Complexity** | ❌ Difficult to configure and wire compared to a simple Star. |

### Visual Representation
```mermaid
graph TD
    Root[Central Hub / Root]
    
    SubA[Secondary Hub A]
    SubB[Secondary Hub B]
    
    PC1[Device 1]
    PC2[Device 2]
    PC3[Device 3]
    PC4[Device 4]
    
    Root ===|Backbone| SubA
    Root ===|Backbone| SubB
    
    SubA --- PC1
    SubA --- PC2
    SubB --- PC3
    SubB --- PC4
    
    style Root fill:#ff9900,stroke:#333
    style SubA fill:#ffff99,stroke:#333
    style SubB fill:#ffff99,stroke:#333
```

**Related:**

- [[Star Topology]] (The building block of a Tree)
    
- [[Bus and Ring Topologies]] (The backbone often acts like a Bus)
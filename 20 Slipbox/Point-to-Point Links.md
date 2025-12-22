---
tags:
  - networking/topology
  - wan
created: 2025-12-10
check: verified
---

# Point-to-Point vs. Multipoint

### Point-to-Point (PtP)
![[point-to-point Topology Diagram.webp]]A direct connection between exactly two devices (e.g., two Routers connecting two buildings).
*   **Use Case:** WAN links, connecting Hybrid topologies together.
*   **Pro:** Reliable, full bandwidth.
*   **Con:** Not scalable (1-to-1 only).

### Point-to-Multipoint (PtMP)
![[point to multipoint Topology Diagram.png]]A central device (like a router) connects to multiple destination nodes.
*   **Use Case:** Corporate HQ connecting to 3 different branch offices.
*   **Risk:** The central device is a Single Point of Failure. Congestion can occur at the "hub" of the connection.

### Related Concept: High Availability (HA)
To solve the "Single Point of Failure" in these topologies, we use **HA**.
*   **Cluster:** Grouping identical devices (e.g., two firewalls) to act as one.
*   If Primary fails, Secondary takes over instantly.
---
tags:
  - networking/segmentation
  - definitions
created: 2025-12-23
check: verified
---

# Collision and Broadcast Domains

Understanding boundaries in a network.

### 1. Collision Domain
*   **Definition:** A segment where data packets can collide if two devices talk at once.
*   **Goal:** You want **MANY** small collision domains.
*   **The Hardware Rule:**
    *   **Hub:** Extends the collision domain (1 Big Domain = Bad).
    *   **Switch:** Breaks the collision domain. **Each Port** is its own collision domain (Good).

### 2. Broadcast Domain
![[Pasted image 20251223123438.png]]
*   **Definition:** The distance a "Broadcast Frame" (FFFF.FFFF.FFFF) travels.
*   **Goal:** You want to limit this to prevent "Broadcast Storms."
*   **The Hardware Rule:**
    *   **Hub:** Extends it.
    *   **Switch:** Extends it (Broadcasts go out every port).
    *   **Router:** **Breaks** the broadcast domain. Routers do not forward broadcasts.

| Device     | Breaks Collision Domain? | Breaks Broadcast Domain? |
| :--------- | :----------------------- | :----------------------- |
| **Hub**    | ❌ No                     | ❌ No                     |
| **Switch** | ✅ Yes (Per Port)         | ❌ No (Unless VLANs used) |
| **Router** | ✅ Yes                    | ✅ Yes                    |
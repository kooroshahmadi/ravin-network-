---
tags:
  - networking/media
  - layer1
  - wiring
created: 2025-12-17
check: verified
---

# Ethernet Wiring Standards

How the 8 wires inside the cable are arranged on the RJ-45 pin.
![[Ethernet Wiring Standards.png]]
### The Standards (T568A vs T568B)
The only difference is the color of the wires. Electrically, they work the same.
*   **T568A:** Green pair is on pins 1 & 2. (Gov/Legacy).
*   **T568B:** Orange pair is on pins 1 & 2. (Most common in business).

### Cable Types
1.  **Straight-Through:**
    *   **Wiring:** T568B on both ends (or A on both ends).
    *   **Use:** Connecting **Different** devices (PC to Switch, Router to Switch).
2.  **Crossover:**
    *   **Wiring:** T568A on one end, T568B on the other. (Swaps Orange and Green).
    *   **Use:** Connecting **Similar** devices (Switch to Switch, PC to PC).

### Auto-MDIX
**Automatic Medium-Dependent Interface Crossover.**
*   Modern network cards detect if you used the wrong cable and electronically swap the signals.
*   *Result:* You rarely need a physical crossover cable anymore.
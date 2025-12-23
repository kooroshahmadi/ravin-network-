---
tags:
  - networking/performance
  - configuration
created: 2025-12-23
check: enriched
---

# MTU and Jumbo Frames

### MTU (Maximum Transmission Unit)
The largest packet size allowed on an interface.
*   **Ethernet Standard:** **1500 Bytes**.
*   **Issue:** If you send a 2000 Byte packet through a 1500 MTU Router, it must **Fragment** (cut in two). This causes CPU load and latency.

### Jumbo Frames (MTU 9000)
Used in **SANs (Storage Area Networks)** or Data Centers.
*   **Size:** Increases MTU to **9000 Bytes**.
*   **Why use them?**
    *   **CPU Efficiency:** Processing headers takes CPU power. Sending 1 big packet (1 header) is easier than 6 small packets (6 headers).
    *   **Throughput:** Great for big file transfers (Backups, Video Editing).
*   **The Risk:** Every device on the path (Server, Switch, Storage) **MUST** support Jumbo Frames. If one doesn't, packets drop.
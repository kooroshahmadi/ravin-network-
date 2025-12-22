---
tags:
  - networking/hardware
  - performance
created: 2025-12-22
check: enriched
---

# Load Balancing and Optimization

### 1. Load Balancer
![[How-Load-Balancer-works.webp]]
A device that distributes traffic across multiple servers (Server Farm).
*   **Virtual IP (VIP):** The user connects to one IP (the Load Balancer), and the LB routes it to Server A, B, or C.
*   **Algorithms:**
    *   *Round Robin:* A -> B -> C -> A.
    *   *Least Connections:* Send to the server doing the least work.
    *   *IP Hash:* User A always goes to Server A (Persistence/Sticky Session).
*   **SSL Offloading:** The Load Balancer handles the heavy encryption/decryption work, letting the web servers focus on just serving content.

### 2. Proxy Server
![[Proxy server.webp]]
*   **Forward Proxy:** Acts on behalf of the **Client** (e.g., Office web filter). "I want to go to Google." -> Proxy goes to Google.
*   **Reverse Proxy:** Acts on behalf of the **Server**. Hides the real web server from the internet (Security/Caching).
*   **Caching:** Storing copies of popular sites to save bandwidth.

### 3. Packet Shaper (Traffic Shaper)
![[packet shaper.png]]
*   **Role:** Manages Bandwidth.
*   **Technique:** Delays less important packets (YouTube) to ensure critical packets (VoIP) get through.
*   **Link:** Closely related to **QoS** (Quality of Service).
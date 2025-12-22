---
tags:
  - networking/security
  - hardware
created: 2025-12-22
check: enriched
---

# Firewalls and NGFW

**Definition:** A security barrier that filters traffic based on rules (ACLs).
![[figure-1-next-generationfirewallcapabilities-797c8da097bea3b405279c8ee3af7a80.webp]]
### 1. Traditional Firewall (Stateful Packet Inspection)
*   **Layer:** Operates at **Layer 3 and 4** (IP and Port).
*   **Logic:** "Allow traffic from IP 10.0.0.1 on Port 80."
*   **Stateful:** It remembers active connections. If you send a request OUT, it automatically allows the reply IN.

### 2. NGFW (Next-Generation Firewall)
![[NGFW deployment scenarios.jpg]]
*   **Layer:** Operates up to **Layer 7** (Application).
*   **Logic:** "Allow 'Marketing Group' to access 'Facebook', but block 'Facebook Games'."
*   **Deep Packet Inspection (DPI):** It looks *inside* the packet payload, not just the header.
*   **Features:** Integrated IPS, SSL Inspection (decrypting traffic to scan it), and User Identity awareness.

| Feature               | Traditional FW | NGFW                  |
| :-------------------- | :------------- | :-------------------- |
| **Visibility**        | IP & Port      | Application & User    |
| **Protection**        | Access Control | Intrusion Prevention  |
| **Encrypted Traffic** | Blind to it    | Can Decrypt & Inspect |
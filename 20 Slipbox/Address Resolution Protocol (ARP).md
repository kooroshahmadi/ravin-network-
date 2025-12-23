---
tags:
  - networking/protocols
  - addressing
created: 2025-12-23
check: verified
---

# Address Resolution Protocol (ARP)

**Role:** The translator between Layer 3 (IP) and Layer 2 (MAC).
*   *Analogy:* "I have the phone number (IP), but I need the GPS coordinates (MAC) to drive there."
![[How-Address-Resolution-Protocol-ARP-works---gif-opt-(1).gif]]
### How it works
1.  **Request:** "Who has IP 192.168.1.5?" (Broadcast: Everyone hears this).
2.  **Reply:** "I am 192.168.1.5, my MAC is AA:BB:CC..." (Unicast).
3.  **Cache:** The sender saves this pair in the **ARP Table** (`arp -a`) so it doesn't have to ask again.

### ARP Commands
*   `arp -a`: View the cache.
*   `arp -d`: Delete the cache (useful if a device changed its NIC).
---
tags:
  - networking/addressing
  - math
created: 2025-12-25
check: enriched
---

# Subnetting and CIDR

**Subnetting** is the process of taking a large network and chopping it into smaller, efficient pieces.

### CIDR Notation (Classless Inter-Domain Routing)
Replaces the old "Class" system. We use a **Suffix** to denote the Subnet Mask.
*   `/24` = `255.255.255.0` (Standard LAN).
*   `/16` = `255.255.0.0` (Large Network).

### The "Magic Formulas"
1.  **Calculate Hosts:** $2^h - 2$
    *   *h* = number of host bits (zeros in the mask).
    *   *-2*: We subtract the **Network ID** (First IP) and **Broadcast Address** (Last IP).
    *   *Example (/24):* 8 host bits. $2^8 = 256$. $256 - 2 = 254$ usable hosts.

2.  **Calculate Subnets:** $2^n$
    *   *n* = number of bits borrowed from the host portion.

### Terminology
*   **Network ID:** The very first IP (`192.168.1.0`). Identifies the group.
*   **Broadcast IP:** The very last IP (`192.168.1.255`). Speaks to everyone.
*   **Default Gateway:** Usually the first usable IP (`192.168.1.1`). The "Door" to the internet.

### Supernetting
The opposite of subnetting.
*   **Subnetting:** Taking a `/24` and making two `/25`s (Dividing).
*   **Supernetting:** Taking two `/24`s and merging them into a `/23` (Summarization). Used to make routing tables smaller.
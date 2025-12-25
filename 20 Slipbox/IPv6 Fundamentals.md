---
tags:
  - networking/addressing
  - ipv6
created: 2025-12-25
check: verified
---

# IPv6 Fundamentals

Designed to solve the "IPv4 Exhaustion" problem.

### Structure
*   **Length:** 128-bit address.
*   **Format:** 8 groups of Hexadecimal (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).
*   **Quantity:** $2^{128}$ addresses (340 Undecillion). Enough for every grain of sand on Earth.

### Shorthand Rules
1.  **Leading Zeros:** `0db8` becomes `db8`.
2.  **Zero Compression:** A string of consecutive zeros can be replaced by `::` (Double Colon).
    *   *Rule:* Can only use `::` **ONCE** per address.

### Key Features
1.  **No Broadcasts:** Replaced by **Multicast**.
2.  **No NAT:** Every device gets a global public IP. NAT is obsolete in IPv6.
3.  **Auto-Configuration (SLAAC):** Devices can generate their own IP using their MAC address (EUI-64).

### Special Addresses
*   **Loopback:** `::1` (Equivalent to 127.0.0.1).
*   **Link-Local:** Starts with `FE80::` (Equivalent to APIPA).
---
tags:
  - cisco/cli
  - verification
created: 2026-01-01
check: enriched
---

# Interface Verification Commands

How to check your work.

### 1. `show ip interface brief`
The "Holy Grail" of verification. It gives a summary of Layer 1 and Layer 2 status.

| Output | Status (L1) | Protocol (L2) | Meaning |
| :--- | :--- | :--- | :--- |
| `Up / Up` | Up | Up | **Working.** Cable connected, config correct. |
| `Down / Down` | Down | Down | **Physical Issue.** Cable unplugged or device off. |
| `Admin Down / Down` | Down | Down | **Shutdown.** You need to type `no shutdown`. |
| `Up / Down` | Up | Down | **Data Link Issue.** Speed mismatch, Encapsulation error, or Keepalives missing. |

### 2. `show interfaces <int>`
Detailed statistics (Errors, MAC address, Speed, Duplex).
*   **Runts/Giants:** Bad hardware or collisions.
*   **CRC Errors:** Cable noise (EMI) or bad cable.

### 3. Interface Description
Labels are vital for troubleshooting 6 months later.
```cli
Switch(config)# interface fa0/1
Switch(config-if)# description Link to HR Printer

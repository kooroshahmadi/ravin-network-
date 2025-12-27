---
tags:
  - security/iam
  - definitions
created: 2025-12-28
check: verified
---

# AAA Framework

**Definition:** The security architecture for controlling access.
*   **Authentication (Who):** Verifying identity (Password, Fingerprint).
*   **Authorization (What):** Verifying permissions (Can you access the Payroll folder?).
*   **Accounting (When):** Logging the activity (User Bob logged in at 9:00 AM).

### The Protocols (RADIUS vs TACACS+)
These protocols speak the "AAA" language between network devices and the central server.

| Feature        | RADIUS                     | TACACS+                                |
| :------------- | :------------------------- | :------------------------------------- |
| **Vendor**     | Open Standard (IETF)       | Cisco Proprietary (Mostly)             |
| **Protocol**   | **UDP** (Ports 1812/1813)  | **TCP** (Port 49)                      |
| **Encryption** | Encrypts **Password Only** | Encrypts **Entire Body** (More Secure) |
| **Separation** | Combines Auth & Author     | Separates Auth, Author, and Account    |
| **Use Case**   | Wi-Fi / VPN Users          | Admin Access to Routers                |
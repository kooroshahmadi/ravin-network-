---
tags:
  - security/iam
  - authentication
created: 2025-12-28
check: enriched
---

# Authentication Types and MFA

### The Factors of Authentication (MFA)
To be considered "Multi-Factor," you must use two **different** categories.
1.  **Something you Know:** Password, PIN, Mother's maiden name.
2.  **Something you Have:** Smart Card, RSA Token, Phone (SMS Code).
3.  **Something you Are:** Biometrics (Fingerprint, Iris, Face).
4.  **Something you Do:** Typing pattern, Signature (Behavioral).
5.  **Somewhere you Are:** GPS Location (Geofencing).

> [!warning] Exam Trick
> Using a Password + a PIN is **NOT** MFA. That is just two "Somethings you Know."
> Password + Fingerprint **IS** MFA.

### Authentication Protocols
*   **Kerberos:** The standard for Windows Domains (Active Directory). Uses **Tickets** and timestamps to prevent Replay Attacks. (Port 88).
*   **LDAP:** Lightweight Directory Access Protocol. The "Phonebook" of the network. (Port 389 / 636 Secure).
*   **802.1x:** Port-based Network Access Control (NAC).
    *   *Supplicant:* The Client (Laptop).
    *   *Authenticator:* The Switch/AP.
    *   *Auth Server:* The RADIUS Server.
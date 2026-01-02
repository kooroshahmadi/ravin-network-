---
tags:
  - cisco/security
  - ssh
  - config
created: 2026-01-02
check: enriched
---

# Configuring SSH on Cisco

**Secure Shell (SSH)** replaces Telnet (TCP 23) because it encrypts the session. Telnet sends everything (including passwords) in clear text.

### Prerequisites (The Setup)
SSH relies on **RSA Keys** (Asymmetric Encryption). To generate a key, the router acts like a Certificate Authority. It needs a unique identity.
1.  **Hostname:** The device must have a name (not 'Router').
2.  **Domain Name:** The device must belong to a domain.
3.  **FQDN (Fully Qualified Domain Name):** The combination of the two.
    *   *Example:* Host `SW1` + Domain `cisco.com` = FQDN `SW1.cisco.com`.

### Configuration Steps
```cli
! Step 1: Set Identity
Switch(config)# hostname SW1
Switch(config)# ip domain-name cisco.com

! Step 2: Generate Keys
! Note: Use 1024 or 2048 bits. <768 is insecure.
Switch(config)# crypto key generate rsa

! Step 3: Force Version 2 (Best Practice)
Switch(config)# ip ssh version 2

! Step 4: Create User
Switch(config)# username admin secret cisco123

! Step 5: Configure Lines
Switch(config)# line vty 0 15
Switch(config-line)# login local        <-- MUST use local DB for SSH
Switch(config-line)# transport input ssh <-- Disables Telnet
```

### How to Connect (The Client)

From a PC or another Router:

- **Command:** ssh -l <username> <ip_address>
    
- **Example:** ssh -l admin 192.168.10.1
    

> [!info] What is RSA?  
> RSA is an algorithm that creates a **Key Pair** (Public and Private). The Router keeps the Private key. You (the client) get the Public key to encrypt your traffic. Only the Router's Private key can decrypt it.


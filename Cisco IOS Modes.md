---
tags:
  - cisco/cli
  - configuration
created: 2025-12-31
check: verified
---

# Cisco IOS Modes

Cisco devices use a hierarchical command structure. You must be in the "Right Room" to do the "Right Job."

### 1. User Exec Mode (`>`)
*   **Prompt:** `Router>`
*   **Access:** The default mode when you log in.
*   **Power:** Very low. Can only "look" (ping, show basic info). Cannot change anything.
*   **Command to leave:** `enable`

### 2. Privileged Exec Mode (`#`)
*   **Prompt:** `Router#`
*   **Access:** Requires the `enable` command (and often a password).
*   **Power:** High. Can see **everything** (passwords, configs) and save changes (`write`), but cannot *edit* the configuration.
*   **Command to leave:** `configure terminal`

### 3. Global Configuration Mode (`(config)#`)
*   **Prompt:** `Router(config)#`
*   **Access:** Requires `configure terminal` (conf t).
*   **Power:** The "Edit Mode." Changes made here affect the **whole device** (hostname, domain name).
*   **Command to leave:** `interface ...` or `exit`.

### 4. Interface Configuration Mode (`(config-if)#`)
*   **Prompt:** `Router(config-if)#`
*   **Access:** `interface gigabitEthernet 0/0`
*   **Power:** Changes affect **only that one port** (IP address, speed, shutdown).

```mermaid
graph TD
    User[User Exec '>'] -- "enable" --> Priv[Privileged '#']
    Priv -- "configure terminal" --> Global[Global Config '(config)#']
    Global -- "interface g0/0" --> Int[Interface Config '(config-if)#']
    
    Int -- "exit" --> Global
    Global -- "end" --> Priv
    Priv -- "disable" --> User
```

Related:
* [[Network Lab Tools]] (You will need Packet Tracer/GNS3 now)

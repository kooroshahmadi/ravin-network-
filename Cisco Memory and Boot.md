---
tags:
  - cisco/hardware
  - boot-process
created: 2026-01-01
check: verified
---

# Cisco Memory and Boot

Understanding where files live is critical for saving configurations.

### Memory Types
| Memory | Type | Content | Volatility | Command to Save |
| :--- | :--- | :--- | :--- | :--- |
| **RAM** | Volatile | **Running-Config** (Current settings) | Lost on Reboot | `write` or `copy run start` |
| **NVRAM** | Non-Volatile | **Startup-Config** (Saved settings) | Saved on Reboot | N/A |
| **Flash** | Non-Volatile | **IOS Image** (.bin file) | Saved on Reboot | N/A |
| **ROM** | Read-Only | **Bootstrap** (POST & Mini-IOS) | Permanent | N/A |

### The Boot Sequence
1.  **POST:** Hardware check.
2.  **Bootstrap:** Loads from ROM.
3.  **IOS Load:** Searches Flash for the OS image.
4.  **Config Load:** Searches NVRAM for `startup-config`.
    *   *If found:* Loads it into RAM.
    *   *If NOT found:* Enters "System Configuration Dialog" (Setup Wizard).

```mermaid
graph TD
    PowerOn --> POST
    POST --> Bootstrap
    Bootstrap --> LoadIOS[Load IOS from Flash]
    LoadIOS --> LoadConfig{Config in NVRAM?}
    
    LoadConfig -- Yes --> Run[Load into RAM]
    LoadConfig -- No --> Setup[Setup Mode]
    
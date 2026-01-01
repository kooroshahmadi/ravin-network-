---
tags:
  - cisco/config
  - security/hardening
created: 2026-01-01
check: enriched
---

# Device Hardening and Passwords

Securing the Management Plane of the device.

### 1. Enable Secrets (Privilege Mode Security)
*   `enable password cisco`: **Legacy.** Stores password in clear text (Type 0) or weak encryption (Type 7). Avoid using this.
*   `enable secret cisco`: **Modern.** Hashes the password using MD5 (Type 5). Always use this.
*   *Rule:* If both are set, `secret` overrides `password`.

### 2. Line Security (Console & VTY)
Two ways to secure a line:
*   **Method A (Shared Password):**
    ```cli
    line console 0
    password cisco
    login              <-- Tells IOS to check the line password
    ```
*   **Method B (Local User Database - Better):**
    ```cli
    username admin secret cisco123   <-- Creates a user in the config
    line console 0
    login local        <-- Tells IOS to check the Username database
    ```

### 3. Encryption Service
*   Command: `service password-encryption`
*   **Function:** It encrypts *all* current and future passwords in the running-config (Type 7).
*   **Weakness:** Type 7 is very weak. It is only meant to stop "Shoulder Surfing" (people reading your screen). It is easily cracked online.

### 4. Usability Commands
*   `exec-timeout 5 0`: Logs you out after 5 minutes of inactivity. (Secures the session).
*   `logging synchronous`: Prevents system log messages (like "Link Up") from interrupting your typing mid-command.
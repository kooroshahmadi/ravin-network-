---
tags:
  - security/attacks
  - crypto
created: 2025-12-27
check: enriched
---

# Password and Encryption Attacks

### 1. Ransomware
*   **Mechanism:** Malware that **Encrypts** the victim's data with a key the victim doesn't have.
*   **Goal:** Extortion. "Pay us 5 Bitcoin to get the decryption key."
*   **Defense:** **Offline Backups**. If you have a clean backup, you don't need to pay.

### 2. Brute Force
*   **Mechanism:** Trying every possible combination of characters (aaaa, aaab, aaac...).
*   **Tools:** *John the Ripper*, *Hashcat*.
*   **Defense:** Account Lockout Policies (Lock account after 3 failed tries).

### 3. Dictionary Attack
*   **Mechanism:** Trying a list of common words (password123, football, monkey). Faster than Brute Force.

### 4. Man-in-the-Middle (On-Path Attack)
*   **Mechanism:** The attacker sits between two communicating parties.
*   **Technique:** Often uses **ARP Spoofing** to trick the victim into sending data to the hacker instead of the router.
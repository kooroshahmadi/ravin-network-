---
tags:
  - security/policy
  - management
created: 2025-12-28
check: enriched
---

# Security Policies and DLP

### Common Policies (The Paperwork)
*   **AUP (Acceptable Use Policy):** The document employees sign saying they won't watch Netflix on work Wi-Fi.
*   **NDA (Non-Disclosure Agreement):** Legal contract protecting trade secrets.
*   **BYOD Policy:** Rules for bringing personal phones to work (Bring Your Own Device).

### DLP (Data Loss Prevention)
Software that stops data from leaking.
*   **Network DLP:** Scans outgoing email for "Credit Card Numbers" or "SSNs" and blocks the email.
*   **Endpoint DLP:** Stops you from copying files to a USB drive.

### Patch Management
The process of keeping software up to date.
*   **The Cycle:** Detect -> Assess -> Test (Sandboxing) -> Deploy -> Verify.
*   **Critical:** You *must* test patches before deploying, or you might crash the production server.
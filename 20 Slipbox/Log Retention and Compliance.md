---
tags:
  - security/compliance
  - laws
  - afta
created: 2025-12-28
check: verified
---

# Log Retention and Compliance

Organizations don't just keep logs for fun; they are legally required to.

### General Global Standards
*   **PCI-DSS (Credit Cards):** Must store logs for **1 year**. (3 months must be "hot" or instantly accessible).
*   **HIPAA (Healthcare):** Must store logs for **6 years**.
*   **GDPR (Europe Privacy):** No specific time, but "as long as necessary."

### AFTA and FATA Rules (Iran Specific)
The **Strategic Management Center for InfoSec (AFTA)** and **FATA (Cyber Police)** enforce strict logging for ISPs and businesses to ensure traceability.

| Requirement | Duration | Purpose |
| :--- | :--- | :--- |
| **Traffic/User Logs** | **Min. 6 Months** | To track who used which IP address at a specific time (NAT Translation Logs). |
| **Financial Data** | **1+ Years** | For banking and transaction fraud investigation. |
| **Hosting Providers** | **6 Months** | Must keep records of who rented a VPS or Domain. |

> [!important] The "Why"
> If a cybercrime occurs, the police will ask: *"Who had IP 5.x.x.x on Tuesday?"*
> If you don't have the **NAT Logs** stored for the required 6 months, the organization can be held liable.


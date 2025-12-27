---
tags:
  - security/operations
  - workflow
created: 2025-12-28
check: enriched
---

# SIEM Workflow and Use Cases

### The Lifecycle of a Log
1.  **Collection:** Gather raw data.
2.  **Normalization:** Standardize the format.
3.  **Correlation:** Connect the dots.
4.  **Alerting:** Notify the human.
5.  **Response:** SOC Analyst investigates.

### Key Use Cases
*   **Brute Force Detection:** "User Bob failed login 10 times in 10 seconds."
*   **Impossible Travel:** "User Alice logged in from Tehran at 9:00 AM and from Moscow at 9:05 AM." (Physically impossible).
*   **Privilege Escalation:** "A junior user suddenly added themselves to the 'Domain Admins' group."
*   **Data Exfiltration:** "A server just sent 50GB of data to an unknown IP at 3:00 AM."
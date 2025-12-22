---
tags:
  - networking/virtualization
  - devops/infrastructure
created: 2025-12-10
---

# Virtualization Basics

In modern networking and DevOps, we distinguish between the metal and the software.

*   **Physical Host:** The actual metal box (Hardware).

*   **Virtual Host (VM):** Software computers running inside the physical host.

### Conceptual Structure

```text
+--------------------------------------------------+
|               PHYSICAL SERVER (Hardware)         |
|  [ CPU ]   [ RAM ]   [ HDD ]   [ NIC ]           |
+------------------------+-------------------------+
|      Hypervisor (Virtualization Layer)           |
+-----------+------------+------------+------------+
|  VM #1    |   VM #2    |   VM #3    |
| (Web Srv) | (Mail Srv) | (DB Srv)   |
| IP: .10   | IP: .11    | IP: .12    |
+-----------+------------+------------+

```


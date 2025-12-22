---
tags:
  - networking/protocols
  - web
created: 2025-12-15
check: enriched
---

# Web and DNS Protocols

### 1. HTTP / HTTPS![[HTTP.gif]]
![[HTTPS-gif.gif]]
*   **Ports:** TCP 80 (HTTP), TCP 443 (HTTPS).
*   **Role:** Transmitting web resources.
*   **HTTPS:** Encrypts traffic using **SSL/TLS**. Ensures **Confidentiality** (No eavesdropping) and **Integrity** (No tampering).

### 2. DNS (Domain Name System)
*   **Port:** UDP 53 (Queries), TCP 53 (Zone Transfers).
*   **Role:** Resolving Names (google.com) to IPs (142.250.x.x).

### The DNS Hierarchy (Tree Structure)
![[root_dns_server.webp]]
1.  **Root (.)**: The top of the tree.
2.  **TLD (Top Level Domain):** `.com`, `.org`, `.edu`.
3.  **Domain:** `google`, `amazon`.
4.  **Subdomain:** `mail.google.com` or `www.google.com`.
*   **FQDN:** Fully Qualified Domain Name (e.g., `www.google.com.`).
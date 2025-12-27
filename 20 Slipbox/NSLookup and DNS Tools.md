---
tags:
  - networking/tools
  - dns
created: 2025-12-27
check: verified
---

# NSLOOKUP Tool

**Name Server Lookup.** Used to query a DNS server directly.

### Modes
1.  **Command Mode:** `nslookup google.com` (Quick check).
2.  **Interactive Mode:** Type `nslookup` and hit Enter. You enter a "shell" to run multiple queries.

### Troubleshooting Commands (Interactive Mode)

| Command | Meaning | Insight |
| :--- | :--- | :--- |
| `server 8.8.8.8` | Change the DNS server you are asking. | "My internal DNS is broken, can I reach Google's DNS?" |
| `set type=mx` | Look for **Mail Exchange** records. | "Why am I not receiving emails?" |
| `set type=ns` | Look for **Name Server** records. | "Who owns this domain?" |
| `set debug` | Show Verbose info. | Shows the TTL and exact packet details. |

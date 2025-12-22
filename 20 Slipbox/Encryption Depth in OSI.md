---
tags:
  - security/encryption
  - networking/advanced
created: 2025-12-10
check: verified
---

# Encryption Depth in OSI

Where you apply encryption changes what parts of the packet are visible to the public network.
![[OSI-Model encryption.webp]]
**Concept:** As you go lower in the layers, you encrypt more of the "Headers."

| Layer Encrypted | Headers Hidden | Protocols Used |
| :--- | :--- | :--- |
| **Layer 7 (App)** | Payload Only | PGP (Email), Data-at-rest |
| **Layer 4 (Transport)** | Payload + TCP Headers | SSL/TLS (HTTPS) |
| **Layer 3 (Network)** | Payload + TCP + IP Headers | IPSec (VPNs) |
| **Layer 2 (Data Link)** | All above + MAC Headers | MACSec (Switch-to-Switch) |
| **Layer 1 (Physical)** | Everything + OTN Headers | Optical Encryption (DWDM) |

> [!tip] Trade-off
> The lower you encrypt, the more secure the metadata is, but the harder it is to route the traffic over the public internet (because routers can't see the IP headers!).

![[Encryption on OSI.png]]
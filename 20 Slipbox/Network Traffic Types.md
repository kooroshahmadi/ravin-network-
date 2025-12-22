---
tags:
  - networking/concepts
  - transmission
created: 2025-12-22
check: enriched
---

# Network Traffic Types

How data is addressed affects who receives it.

| Type          | Analogy      | Description                                                                                                | Addressing                                                  |
| :------------ | :----------- | :--------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------- |
| **Unicast**   | Phone Call   | **One-to-One.** Data is sent from one specific source to one specific destination.                         | Uses a specific Destination IP/MAC.                         |
| **Broadcast** | Megaphone    | **One-to-All.** Data is sent to *everyone* on the network segment (LAN).                                   | Dest IP: `255.255.255.255`<br>Dest MAC: `FF:FF:FF:FF:FF:FF` |
| **Multicast** | Subscription | **One-to-Many.** Data is sent to a specific *group* of interested devices (e.g., watching a video stream). | IP Range: `224.0.0.0` to `239.255.255.255`                  |
| **Anycast**   | 911 Call     | **One-to-Nearest.** Request is sent to the *closest* available server (used in DNS and CDN).               | Same IP exists in multiple locations.                       |
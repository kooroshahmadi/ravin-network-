---
tags:
  - networking/hardware
  - definitions
created: 2025-12-10
---

# Network Host Types

A **Host** is any device on a network that possesses an **IP address** and is capable of sending or receiving data.

### The Three Main Classifications

1. **Client Host:** Requests services (e.g., Laptop, Smartphone).
2. **Server Host:** Provides services (e.g., Web Server). See [[Server Roles]].
3. **Networking Host:** Connects the others (Intermediaries like Routers/Switches).

### Interaction Flow
```mermaid
sequenceDiagram
    participant Client as Client Host (Laptop)
    participant Net as Networking Host (Switch/Router)
    participant Server as Server Host (Web Server)

    Client->>Net: 1. Request: "Open google.com"
    Net->>Server: 2. Forward Request
    Note over Server: Processing...
    Server->>Net: 3. Response: "Here is the website"
    Net->>Client: 4. Deliver Data
```

**Related:**

- [[Virtualization Basics]]
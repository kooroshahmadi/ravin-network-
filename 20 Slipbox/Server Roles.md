---
tags:
  - networking/servers
  - protocols
created: 2025-12-10
---

# Server Roles

A Server is a centralized computer running a **Network Operating System (NOS)**. While hardware is important, the *Role* is defined by the service it provides.

| Server Type | Function | Protocol Example |
|---|---|---|
| **Mail Server** | Handles email routing & storage | SMTP, IMAP |
| **Web Server** | Hosts websites & apps | HTTP, HTTPS |
| **File Server** | Centralized file storage | SMB, NFS |
| **Print Server** | Manages print queue | IPP |


```mermaid
graph LR
    User((User))
    
    subgraph "Server Farm"
    Web[Web Server]
    Mail[Mail Server]
    File[File Server]
    end
    
    User -- "View Website" --> Web
    User -- "Send Email" --> Mail
    User -- "Save Document" --> File
---
tags:
  - networking/protocols
  - email
created: 2025-12-15
check: verified
---

# Email Protocols

The trio of protocols that move mail.

### 1. SMTP (Simple Mail Transfer Protocol)
![[SMTP-Gif.gif]]
*   **Ports:** TCP 25 (Unsecured), 587 (TLS/Auth).
*   **Role:** **SENDING** mail.
*   **Flow:** Client -> Server, or Server -> Server.

### 2. POP3 (Post Office Protocol v3)
![[pop3.jpg]]
*   **Ports:** TCP 110 (Unsecured), 995 (SSL).
*   **Role:** **RECEIVING** mail.
*   **Behavior:** Downloads email to local device and (usually) deletes it from the server. Bad for multiple devices.

### 3. IMAP (Internet Message Access Protocol)
![[Internet-Message-Access-Protocol-(IMAP).gif]]
*   **Ports:** TCP 143 (Unsecured), 993 (SSL).
*   **Role:** **RECEIVING** mail.
*   **Behavior:** Syncs email. Mail stays on the server. Good for multiple devices (Phone + Laptop).
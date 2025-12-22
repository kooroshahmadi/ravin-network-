---
tags:
  - networking/osi
  - applications
created: 2025-12-10
check: verified
---

# OSI Upper Layers (7, 6, 5)

These layers are "Host Layers"—they deal with the data before it enters the network.
![[OSI Upper Layers.png]]
### Layer 7: Application
*   **Role:** The interface between the user and the network. This is where APIs live.
*   **Misconception:** The browser (Chrome) is *not* Layer 7. The protocols the browser *uses* (HTTP, HTTPS) are Layer 7.
*   **Protocols:** HTTP, FTP, DNS, SMTP, SSH.

### Layer 6: Presentation
*   **Role:** The "Translator." It ensures data is in a readable format for the Application layer.
*   **Key Functions:**
    1.  **Translation:** converting EBCDIC to ASCII.
    2.  **Encryption:** SSL/TLS encryption often initiates here.
    3.  **Compression:** ZIP, JPEG, formatting.

### Layer 5: Session
*   **Role:** The "Traffic Cop" for applications. It manages the conversation (Dialog Control).
*   **Key Functions:**
    *   **Separation:** Keeps data from Chrome Tab 1 separate from Chrome Tab 2.
    *   **Modes:**
        *   *Simplex:* One way (Radio).
        *   *Half-Duplex:* One at a time (Walkie-Talkie).
        *   *Full-Duplex:* Both ways simultaneously (Telephone).


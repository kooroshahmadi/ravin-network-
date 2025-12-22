---
tags:
  - networking/protocols
  - file-transfer
created: 2025-12-15
check: verified
---

# File Transfer Protocols

Protocols specifically designed to move files between machines.

### 1. FTP (File Transfer Protocol)
![[File-Transfer-Protocol-and-HTTPS-gif-2.gif]]
*   **Ports:** TCP 20 (Data), TCP 21 (Control/Commands).
*   **Function:** Authenticated transfer of files and directory management.
*   **Security:** ❌ **None.** Sends passwords in Clear Text.
*   **Limitation:** Can copy/move files, but **cannot execute** remote programs.
![[filetransfer protocol diagram.jpg]]
### 2. SFTP (Secure FTP)
![[sftp.png]]
*   **Port:** TCP 22 (Runs over SSH).
*   **Function:** Same as FTP, but fully encrypted.
*   **Note:** Not to be confused with FTPS (FTP over SSL).

### 3. TFTP (Trivial FTP)
![[tftp.jpg]]
*   **Port:** UDP 69.
*   **Function:** A stripped-down, lightweight version of FTP.
*   **Use Case:** Network device firmware updates (Cisco IOS) and PXE Booting (installing Windows over a network).
*   **Features:** No authentication, no directory browsing. Very fast.

### 4. SMB (Server Message Block)
*   **Ports:** TCP 445 (Modern), UDP 137-139 (NetBIOS Legacy).
*   **Function:** Windows File & Printer Sharing.
*   **Key Feature:** unlike FTP, SMB **can execute** remote programs.
*   **Linux version:** Known as "Samba."
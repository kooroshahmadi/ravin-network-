intro-protocols:  
protocol: a set of rules & standards that dictate how data must be transferred between devices.  
exp: we have a device in Iran and another in Russia. these two want to communicate with each other. they don't speak each others language so they speak in a international language like English which both can speak with.

File Transfer Protocol (TCP 20, 21):  
purpose: FTP is used to transfer files between machines over an IP network.  
Dual Function:  
as a protocol, it is used by applications to transfer files.  
as a program, it allows users to manually manage files, such as moving, copying, and accessing directories.  
directory operations: FTP supports accessing both files and directories, as well as directory operations like relocating files.  
authentication: users must log in with a username and password for authentication.  
manual usage:  
as a program, FTP can list directories, manipulate files, view file contents, and copy files between hosts.  
cannot execute remote files as a programs.  
security issue:  
FTP sends data in clear text, meaning it is not secure.  
for secure transfer, sftp (secure FTP) is used instead  
it has two ports - 20 & 21, it will use one to create a session based on the used username and password to see if the user has the needed ACL and an answer will be replied and the other for downloading and uploading files.

Telnet (TCP 23):  
purpose: Telnet is used for terminal emulation, allowing a remote client to access another machine's resources.  
client-server model:  
the user operates from a telnet client.  
the resources are accessed from a telnet server.  
functionality:  
telnet makes the client machine appear like a terminal connected to the local network.  
this creates a virtual terminal that allows interaction with the remote host.  
text-mode interaction: the terminal is text-based and can display menus, allowing users to choose options and access applications on the remote server.  
session start: a telnet session is initiated by running the telnet client software and logging into the telnet server.  
security: telnet does not provide security or encryption. for secure remote access, secure shell (SSH) is used as a replacement.  
telnet is not secure - clear text.

SSH (TCP 22):  
secure shell is a secure network protocol used for encrypted remote access to other systems. it replaces telnet and other unencrypted remote management methods.  
features:  
encrypted communication: prevents eavesdropping and malicious attacks.  
strong authentication: uses usernames, passwords, or public/private key authentication.  
secure file transfer: supports SFTP and SCP (secure copy protocol)  
tunneling (port forwarding): allows secure transmission of other protocols through an encrypted SSH channel.

Trivial File Transfer Protocol (TFTP) - UDP 69:  
tftp is a simplified version of ftp designed for quick and easy file transfers when the exact file location is known. it is commonly used for network device configurations, firmware updated, and PXE booting  
features & limitations:  
lightweights & fast: requires minimal overhead, making it faster that FTP.  
easy to use: does not require complex commands or authentication.  
limited functionality:  
no directory browsing capabilities.  
only allows sending and receiving files.  
sends smaller data blocks compared to FTP.  
no authentication & security

SCP & TFTP are p2p file sharing protocols.  
FTP & SFTP are client server protocols

Simple Mail Transfer Protocol (SMTP) - TCP 25:  
SMTP is the standard protocol for sending emails across network. it operates using a queued (spooled) mail delivery system, meaning emails are stored temporarily before being delivered.  
key features:  
handles outgoing emails.  
works with other protocols (e.g., POP3 & IMAP) for receiving emails.  
common ports used:  
TCP 25 - default SMTP port (often blocked by ISP to prevent spam).  
TCP 587 - used for sending emails securely with authentication.  
TCP 465 - smtp with ssl/tls encryption.  
smtp vs. POP3/IMAP:  
smtp, sending emails, 25/ 587/ 465, no encryption by default, ca use ssl/tls  
POP3, receiving emails, 110 / 995, downloads emails to local device  
IMAP, receiving emails, 143 / 993, keeps emails on the server for remote access

Remote Desktop Protocol (RDP) - TCP/UDP 3389:  
RDP (remote Desktop Protocol) is a proprietary protocol developed by Microsoft that allows users to remotely access another computer with a graphical user interface (GUI), unlike telnet, which only provides a command-line interface.  
well-known protocols:  
full GUI access: unlike telnet or SSH, RDP provides a full remote desktop experience.  
cross-platform support: available for windows,, maxOS, and some Linux distributions.  
secure remote access: supports encryption, authentication, and session control.  
components of RDP:  
remote desktop services (RDS): the server-side software that allows remote connection (previously called terminal services).  
remote desktop connection (RDC): the client application used to connect to an RDP server (formerly called terminal services client).

Simple Network Management Protocol (SNMP) - UDP 161, 162:  
SNMP is used for monitoring and managing network devices such as routers, switches, servers, and printers. it allows network administrators to collect, modify, and analyze network performance data.  
how it works:  
polling & data collection: the SNMP management station queries network devices at fixed random intervals to collect status information.  
baseline reporting: snmp establishes a baseline, which represents the normal operational characteristics of the network.  
event notifications: when an issue occurs snmp agents (installed on devices) send an alert (trap) to the management station for quick response.  
ports used:  
UDP 161 - used for polling and communication between snmp manager and agents.  
UDP 162 - used for receiving traps (alerts) from snmp agents.

Hypertext Transfer Protocol (HTTP) - TCP 80:  
HTTP is the foundation of web communication, enabling the transfer of web pages, images, text, videos, and other resources between a web browser (client) and a web server. it allows users to access and interact with websites by clicking links that requests specific resources.  
features & characteristics:  
stateless protocol: each HTTP requests is independent; the server does not remember previous requests.  
supports multimedia content: handles text, images, videos, and interactive elements.  
works with various web technologies: used in combination with HTML, CSS, JavaScript, and API's

Hypertext Transfer Protocol Secure (HTTPS) - TCP 443:  
HTTPS is the secure version of HTTP that encrypts communication between a web browser and a web server using SSL/TLS (Secure Socket Layer / Transport Layer Security). it ensures data integrity, confidentiality, and authentication, making it essential for secure online transactions.  
features & benefits:  
encryption: protects sensitive data (passwords, credit card info) form eavesdroppers.  
authentication: verifies that the website is legitimate and prevents impersonation.  
data integrity: ensures that data is not modified during transmission.

Network Time Protocol (NTP) - UDP 123:  
is a protocol designed to synchronize the clocks of computers and devices across a network to a precise time source, such as an atomic clock. accurate timekeeping is essential for logging events, security protocols, and preventing data inconsistencies.  
importance of NTP:  
ensures accurate timestamps for logs, transactions, and databases.  
prevents data inconsistencies caused by time discrepancies.  
essential for security protocols (e.g., authentication, encryption).  
minimizes network issues caused by unsyncronized devices.

Server Message Block (SMB) - TCP 445, NetBIOS (TCP 137, 139 / UDP 137, 138):  
a protocol used for file and printer sharing, network browsing, and inter process communication on Microsoft windows networks. it allows devices to access shared resources such as files, folders, and printers over a network.  
importance of NTP:  
ensures accurate timestamps for logs, transactions, and database.  
prevents data inconsistencies caused by time discrepancies.  
essential for security protocols (e.g., authentication, encryption).  
minimizes network issues caused by unsyncronized devices.

SMB can execute programs while FTP and SFTP cannot execute

Domain Name System (DNS) - UDP 53:  
a protocol used to resolve human-readable domain names (like [www.example.com](https://www.google.com/url?sa=E&q=http%3A%2F%2Fwww.example.com)) into their corresponding IP addresses (such as 192.168.1.1). this makes it easier for users to access websites and services without needing to remember numeric IP addresses.

DNS is hierarchic (Gemini add more information)

Dynamic Host Configuration Protocol (DHCP) - UDP 67, 68:  
is used to automatically assign IP addresses and other network configuration settings (like subnet mask, default gateway, DNS servers) to devices on a network. this reduces the need for manual IP configuration.  
how it works:  
DHCP discovery: a client device sends a broadcast request (DHCPDISCOVER) looking for a DHCP server.  
DHCP offer: the DHCP server replies with an offer (DHCPOFFER) containing an available IP address and configuration info.  
DHCP requests: the client responds with a request (DHCPREQUEST) to accept the offered setting.  
DHCP acknowledgment: the server sends a final confirmation (DHCPACK), and the device is configured.  
ports used:  
UDP 67 - used by DHCP server to receive requests from clients.  
UDP 68 - used by the DHCP client to receive responses from the server.
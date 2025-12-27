 Authentication and Access Control:

what is Authentication?
	Authentication is the process of verifying the identity of a user or device. it ensures that the person or system is who they claim to be. this can be done through:
		Passwords
		Smart cards
		Biometric data
			Example: Logging into a system with username and password.
What is Access Control:
	Access Control defines what users are allowed to do once authenticated. it restricts access to systems, files, and functions based on roles or permissions.
		Example: only the finance team can edit budget spreadsheets.
Difference Between Authentication and Authorization:
Concept, Question Answered, Purpose
Authentication, Who are you?, identity verification
Authorization, what are you allowed to do, grants or restricts permissions.

Security Filtering:
	Access Control Lists (ACLs)
	ACLs are sules applied to router or switch interfaces that define whether packets are permitted or denied based on:
		Source IP address
		Destination IP address
		Protocol or port numbers
	Types:
		Standard ACl: Filters by source IP only.
		Extended ACL: Filters by source, destionation, protocol, and port.
	Tunneling:
		Tunneling is the process of encapsulation traffic in a secure wrapper for transmission over insecure networks.
		Used in VPNs (GRE, IPsec, L2TP).
	Encryption:
		Encryption ensures confidentiality of data in transit or at rest.
		Symmetric (e.g., AES)
		Asymmetric (e.g.,RSA)
	Remote Access:
		Remote Access allows administrators to connect to a network from external locations.
		Common protocols: SSH, VPN, RDP.
		Requires secure authentication and encryption.

Managing User Account and Password Security:
	Managing User Accounts:
		Administrators should control who can access systems, define roles, and disable unused or orphaned accounts.
	Managing Passwords:
		Password policies must be enforced:
			Minimum length.
			Complexity requirements.
			Periodic expiration.
			Prohibit reuse of old passwords
		Single Sign-On (SSO):
			Allows users to authenticate once and access multiple systems.
			Improved usability.
			If compromised, attacker gains board access.
		Local Authentication:
			Authentication data is stored locally on the device.
			Suitable for standalone or limited-access systems.
	LDAP:
		Protocol for accessing user information in directories like Microsoft Active Directory. used for centralized authentication.
	Certificates:
		Used in public key infrastructure for validating user identity and securing communications (SSL/TLS).
	Multifactor Authentication (MFA):
		Requires two or more authentication factors:
			Something you know
			something you have
			something you are
			Strongly improves security posture.

User-Authentication Methods:
	Public Key Infrastructure (PKI):
		Framework for issuing and managing digital certificates.
		Used for:
			Securing web traffic (HTTPS).
			Digital signatures.
			Certificate-based login.
	Kerberos:
		Ticket-based authentication protocol used in Windows domains.
		Central authority: KDC (Key Distribution Center).
		Credentials are never sent in plain text.
	AAA (Authentication, Authorization, Accounting)
		Three-layer access control model:
			Authentication: Validating Identity.
			Authorization: Granting appropriate access
			Accounting: Logging activities
				used with protocols like Radius or TACAS+.
	Web Services:
		Modern apps use API-based authentication with protocols such as OAuth 2.0 and OpenID Connect.
	Unified Voice Services:
		Authentication for VoIP Systems using SIP-based mechanisms.
	Network Controllers:
		Centralized authentication for wired/wireless devices via platforms like Cicso DNA Center.

Network Access Control (NAC) & Challenge-Based Protocols:
	Network Access Control (NAC):
		A security framework to enforce access policies based on user, device, locations, or security posture.
			Capabilities:
				Block infected or non-compliant devices.
				Guest User isolation.
				Integration with antivirus, firewall and MDM tools
				popular tools: Cisco ISE, Aruba clearpass
	IEEE 802.1x:
		Standard for port-based Network access control.
		used EAP for authentication exchange
		Roles:
			supplicant (user device)
			Authenticatior (switch or access point)
			Authentication server (e.g., RADIUS)
	Challenge-Based Protocols:
		Authentication via challenge-response methods.
		Examples:
			CHAP (Challenge Handshake Authentication Protocol)
			EAP-CHAP / EAP-TLS
			MS-CHAPv2 (used in windows domains)
			More secure tha password-only methods.
	Posture Assessment:
		Device compliance check before granting network access (anitvirus status, OS version, firewall, etc.). Often built into NAC systems.


Authorization Models (RBAC, ABAC, DAC):
	RBAC - Role-Based Access Control
	Access is granted based on the user's tole withing the organization.
	Example: All finance team members have access to the payroll folder.
	Pros:
		Easy to manage
		Organizationally aligned
	Cons:
		Less flexible in complex scenarios
	ABAC-Attribute-Based Access Control
		Access is determined by evaluating attributes of:
			The user
			The resource
			The environment
	Pros:
		Highly flexible and scalable
	Cons:
		Complex to implement and maintain
	DAC - Discretionary Access Control:
		The owner fo a resource determines who can access it.
		Example: A user shares a spreadsheet with a colleague.
	Pros: User-level control and flexibility
	Cons:
		Risk of accidental exposure of misuse


Identity Federation & Single Sign-on (SSO):
	Identity Federation:
		A trust relationship that allows users to access multiple systems with a single digital identity.
		The user logs in through an identity provider (Idp), and other services trust the authentication.
	Common Standards:
		SAML
		OAuth 2.0
		OpenID Connect
			example: Logging into Zoom using you Google account.
	Pros:
		no need for multiple account
		simplified corss-organization authentication.


Identity Federation & Single Sign-on (SSO):
	Single Sign-On (SSO):
	Login once to gain access to multiple related services.
	example:
		Accessing Outlook, Teams, and OneDrive after logging into Microsoft 365.
	Pros:
		Improved user experience
		Reduces password-related attacks
		Easier account management
	Cons:
		if the central account is compromised, all services are at risk
		Requires strong backend security (MFA, monitoring, etc.)


AAA - Authentication, Authorization, and Accounting:
	What is AAA:
		AAA is a security framework that provides:
			Authentication - Verifies who you are (via username/password, token, digital certificate, etc.)
			Authorization - Determines what you are allowed to do (network access, specific commands, services, ...)
			Accounting - Logs what 
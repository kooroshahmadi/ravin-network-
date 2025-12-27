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
	
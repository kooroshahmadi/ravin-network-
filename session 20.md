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
			Accounting - Logs what you did, when you did, and for how long.
	Common AAA Protocols:
		RADIUS
		TACACS+
	Use Case:
		Remote login to reouters/switches
		VPN access control
		Role-based access and detailed activity logging.

Data Loss Prevention (DLP):
What is DLP:
	DLP refers to technologies and policies designed to prevent sensitive data from leaving the organization. it protects:
		Personally Identifieble Information (PII)
		Financial or health records
		Intellectual property
	Types of DLP:
		Network DLP - monitors outbound network traffic.
		Endpoint DLP - Controls user activity on devices.
		Cloud DLP - Protects data in cloud platforms
	Why is DLP Important:
		Prevents accidental or malicious data leakage.
		Helps meet compliance requirements
		Reduces risk of data breaches and reputational damage.

Mobile Device Management (MDM):
	What is MDM:
		MDM refers to a set of tools and policies used to manage, control, adn secure monile devices like smartphones, tablets, and laptops connected to the corporate netwrok
	Key Functions:
		configure devices (WI-Fi, VPN, Email, etc)
		Enforce security policies (password rules, data encryption)
		Control access to corporate resources
		Remote lock or wipe in case of loss or theft
		Monitor apps and manage software updates
	Benefits of MDM for organizations:
		secure data on BYOD devices
		Enforce control over corporate resource usage
		Quick response to device-related security threats
		Maintain compliance with legal and internal policies


Patch Management:
	Patch Management is the process of installing and managing software software update to fix bugs, close security vulnerabilities, and improve performance.
	Why patch management matters:
		enhances security: prevents exploitation of known vulnerabilities
		improves system stability: reduces crashes and malfunctions
		compliance: helps meet legal and organizational standards
		Centralized control: ensures all systems are uniformly updated
	Key steps in the process:
		identify outdated software
		assess patch risks and relevance
		test parches in a sandbox/test environment
		Deploy patches during low-usage windows
		monitor outcomes and maintain logs.

Security Awareness Training:
	What is Security awareness Training:
		Security Awareness Training is a continuous process that educates employees to :
			recognize security threats
			follow best practices
			properly respond to attacks such as phishing, social engineering, and malware
		Why its Crucial:
			users are the weakest link in the security chain
			90% of breaches stem from human error
			helps prevent users from falling for malicious email or links
			Improves compliance with internal security policies
		Key Training Topics:
			Phishing recognition and response
			strong password habits
			Handling unknown devices
			BYOD and access policy awareness
			prompt incident reporting procedures

Mobile Device Security:
	what is mbile device security:
		mobile device security involves policies, technologies, and procedures to protect smartphones, tablets, and laptops from cyber and physical threats.
	Why is matters:
		Devices often connect to unsecured public networks
		phishing, malware, and physical theft target mobile users
		Sensitive data may be stored on transmitted via mobile devices.
	Key Security measures.
	enable full device encryption
	use strong screen locks
	employ mobile device management
	avoid connection to untrusted public Wi-Fi
	regularly update OS and applications


Security policies and procedures:
	Definition: securiyt policies adn provedures are a set of rules, standards, adn guidelines designed to manage adn safeguard an organizations information assests. they help maintain confidentiality, integrity, adn availability of data.
	why it matters;
		defines user responsibilities and scceptanle behavior
		minimizes human error and insider threats
		provides a framework fo rincident response and accountability
		supports compliance and audit requirements.
common policies & procedures.
policy type, description
acceptable use policy,  outline acceptable and prohibited uses of IT resources
password policy, enforces complexity and change requirments for passwords
incident response policy, guides the organizations response to security incidents
remote access policy, governs secure remote connectivity to internal systems
data classification policy, defiens levels of data sendivity and appropriate handlign



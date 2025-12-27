Introduction:
	Key Objective:
		Understand the concept and structure of Syslog.
		Configure Syslog on Cisco network devices.
		Get familiar with Syslog server tools.
		Analyze log data to detect issues or attacks.
		Learn best practices in log management.
	Expected Outcomes:
		By the end of this session, learners should be able to :
			configure Syslog logging on routers and switches.
			Choose the right Syslog server tool.
			Interpret log messages for troubleshooting.
			Identify and respond to basic network events.
	Why Syslog Matters:
		Logs are the first line of defense for detecting network events and attacks.
		They are essential for audits, compliance, and operational visibility.
		Syslog is a widely supported, lightweight method for centralized logging.

What is Syslog?
	Definition:
		a standardized protocol used to send log and event messages form network devices to a central log server.
	How it Works:
		Devices generate log messages.
		Logs are sent to a Syslog server using UDP port 514.
		Admins use this server to review and analyze logs centrally.
	Syslog Message Structure:
		A typical Syslog message includes:
			Timestamp.
			Hostname.
			Facility & severity level.
			Descriptive message.


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

Syslog Severity Levels:
	What is severity?
		it indicates the criticality of the event. Syslog defines 8 severity levels (0 -7).
	Severity Table:
		level, name, description
		0, emergency, system is unusable.
		1, alert, immediate action required
		2, critical, critical condition but still recoverable
		3, error, non-critical error occurred
		4, warning, potential issue, may escalate
		5, notice, important event, not an error
		6, informational, general operational messages (boot, login, ...)
		7, debug, debug-level messages for developers

Syslog Message Structure:
	A typical message looks like: 
		<PRI> timestamp hostname tag: message
		component, Description
		<PRI>, Encoded priority (facility x 8 + severity)
		timestamp, time of the event
		hostname, source device name or IP
		tag, process or module gengerating the log
		message, description of the event
	Real example: 
		<189> Jan 14 10:24:01 router01 SSHD[12345]: Login succesful from 192.168.1.100
	Explanation:
		<189> => facility 23 (local7), severity 5 (Notice)
		Jan 14 10:24:01 => time
		router01 => hostname
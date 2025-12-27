SIEM (Security Information and Event Management):
	SIEM is a combination of:
		SIM (Security Information Management): log collection and storage.
		SEM (Security Event Management): real-time event analysis and correlation.
	Purpose of SIEM:
		Aggregate logs from diverse sources.
		Analyze, correlate, and generate alerts.
		Enable visibility across the infrastructure.
		Support compliance and forensics.
	SIEM is the brain and eyes of the Security  Operations Center (SoC):
		it helps detect threats like internal misuse, external intrusions, and compliance violations.
	Example:
		SIEM receives logs from a firewall, a Windows server, and antivirus software. it detects:
			Multiple failed login attempts form the same IP.
			Antivirus detection of a suspicious script.
				SIEM correlates the events and raises an alert for a potential brute-force or lateral movement attack.

Key Components of a SIEM System:
	Core Components Explained:
		Log collection: collects logs from devices (firewalls, servers, endpoints) using agents, syslog, API, or SNMP.
		Normalization: Converts logs from various formats into a standard structure for unified analysis.
		Correlation Engine: Detects patterns and relationships between events across different systems to identify threats.
		Alerting: Sends alerts when suspicious or predefined patterns are detected, either via dashboards, email, or integration with ticketing systems.
		Dashboards & Reports: Visual interface to monitor system activity and generate compliance/audit reports.
		Log Storage: Retains logs for months/years based on compliance requirements (e.g., PCI-DSS, GDPR).
	Example:
		a Windows server logs multiple failed login attempts. A firewall logs a blocked IP shortly after. SIEM correlates both, identifies the source IP as potentially malicious, and triggers an alert to the security team
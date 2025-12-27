Network discovery:

NMAP:
	 discovery and scanning with nmap:
		 an attacker wants to understand the topology of the target network.
			 internet connectivity, perimeter networks
			 internal network (with access form modem or wireless access point)
			 can reveal vulnerabilities (or at least disclose the network architecture)
			Nmap can be used for network mapping and port scanning:
				Written by gyodor and the nmap development team
				available for linux, macos, and windows
				we will look at network mapping first, and then port  scanning.



Sweeping for network mappinga:
	sweeping through address space to identify active hosts on the network.
	attacker sends an ICMP echo request to a range of IP addresses.
		if sometheing replies, that address is in use by some target system.
		if nothing replies, that address is not in use, or there is network filtering.
	by default, nmap sweeps each target address befor port scanning using host directory
		can be skipped for greater accuracy -Pn but will slow down the scan
	run nmap as root for best results.

Port Scanning:
	port scanners are a must for any attacker's toolbox.
	they help identify openings on a system adn the type of system
		allowing an attacker to focus an attacak
	most internet applicaitons user TCP or UDP


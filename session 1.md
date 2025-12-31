Ethernet:
	Definition: all networks that are based on twisted pair or fiber optic cables.
	IEEE 802.3
	Cisco's Ethernet switches and two models, fix and modular:
		fix: the number of ports on the switch is fixed and cannot be changed.
		modular: the ports on the switch can be changed using moduls that will slide in the device.
	Port Types:
		FastEthernet 0/0
		FastEthernet 0/1
		GigabitEthernet 0/0
		GigabitEthernet 1/0/1
		TenGigabitEthernet 1/1
		module => Interface TYPE Module Number/Interface number
	Switch:
		Layer2
		Layer3 => MLS (MultiLayer Switch)
	Switch Responsibility:
		Is to forward frames between devices.
		a Switch will decide its actions based on its MAC Address Table.
		a Switch will forward frames based on destination MAC address.

lets go through a scenario:
	we have a network with star topology and we want to ping a device on that network.
	first on layer 3 we have the ip but there is no MAC address to icmp will be frozen in ram and arp will come into play. arp has the mac address of the source but not the destination. for instead of the destination mac address it will put ff:ff:ff:ff:ff:ff (this is the broadcast MAC address). and will broadcast in the network, by this the switch will get a reply by the destination and will learn the the mac address of the 
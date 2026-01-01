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
	first on layer 3 we have the ip but there is no MAC address to icmp will be frozen in ram and arp will come into play. arp has the mac address of the source but not the destination. for instead of the destination mac address it will put ff:ff:ff:ff:ff:ff (this is the broadcast MAC address). and will broadcast in the network, by this the switch will get a reply by the destination and will learn the the mac address of the destination. so now the switch knows the mac address of the source and destination. and by this the message will now not be broadcasted and unicasted back to the source. Gemini add more info and fill in the gaps.

Cisco's OS is IOS (Internetwork Operating System) written in C.
Accessing the Cisco IOS CLI is done by a cable known az the console cable (also known as role over cable). one side is a RS232 also known az serial port and the other is RJ-45. the other way of accessing is telnet or SSH. older hardware just had a RJ-45 cable while newer devices also have a mini USB cable is well.
by defualt Cisco Switches dont need configuring, but configuring is recommended 
now in these days there are some ways of connecting to a switch:
	1. serial port to RJ-45 => rollover cable.
	2. a usb cable to a usb converter to a rollovercable.
	3. usb cable
	4. RJ-45 to USB
Cisco switches operate at 9600rate

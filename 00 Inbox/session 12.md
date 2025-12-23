Internet Protocol Addressing (IP):


Overview of NIC (Network Interface Card):
	Definition:
		a network interface card is a hardware component that allows a device to connect to a network, either wired or wireless.
	How it Works:
		the nic facilitates data transmission and reception over the network by converting data between the digital form used by the computer and the signal form used on the network
	Types of NIC:
		Ethernet NIC's: for wired connections (RJ45 connections).
		Wireless NIC's (Wi-Fi cards): for wireless connections.
	Characteristics: 
		each NIC has a unique MAC address for identification on the network.
	can support speeds like 10/100/1000 Mbps for Ethernet  or up to 10 Gbps in high-end models.
	Why it's important:
		the NIC is vital for network communication, allowing devices to connect and transfer data over both local and wide-area networks.

Overview of MAC Address:
	Definition: a MAC (Media Access Control) address is a unique identifier assigned to a network interface card for communication on the physical network layer.
	Format: Typically consists of 6 pairs of hexadecimal digits (e.g., 00:1A:2B:3C:4D:5E).
	How it Works: the MAC address is used by devices to identify each other on a local network. it's used for data link layer communication (layer 2 of OSI).
	Characteristics: Globally unique and assigned by the hardware manufacturer.
	Permanent

mac address is unchangable by default
using ip config you see your devices IP
IP has 4 oted. each octed is 8bits. in total 32bits
each bit is either 1 or 0

IP classes:
A => 0 - 126 => 0.0.0.0 - 126.255.255.255
B => 128 - 191 => 192.0.0.0 - 191.255.255.255
C => 192 - 223 => 192.0.0.0 - 223.255.255.255
D => 224 - 239 => 224.0.0.0 - 239.255.255.255
E => 240 - 254 => 240.0.0.0 - 254.255.255.255

A, B, C => private addresses
D => multicasting
E => reserved

APPIPA IP
LOOPBACK IP

others are classless IP's

Private IP:
10.0.0.0 - 10.255.255.255
172.16.0.0 - 122.16.255.255
192.168.0.0. - 192.168.255.255


127.0.0.0 - 127.255.255.255 loopback ip range, with this the device will refer to it self

192.168.100.10/24 - this means that the first 24 bits are static. so it will be like this
11111111.11111111.11111111.xxxxxxxx
the first 24 bits are 1 !
in this example if we calculate the IP it will be 255.255.255.0 and this is called subnet mask
network ID
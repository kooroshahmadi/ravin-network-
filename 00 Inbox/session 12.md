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
network ID - the static part of an ip is net ID
and the dynamic part is hsot ID
how to calculate available ip addresses => we take the static part of the IP (for example 255.255.255.0) and 32. then we take away the static part form 32. so in this example 32-24=8, then we take 2 and power it by the answer, so 2 ^ 8 => 256. then we take 256 - 2 which will give us 254 available IP's.
in 192.168.100.0 example
	the FIP (first ip) is 192.168.100.1
	the broadcast ip is 192.168.100.255
	the end ip is 192.168.100.254

Overview of Defaul Gateway:
	Definition: a network device (usually a router) that acts as an intermediary for forwarding packets from a local network to external networks, including the internet.
	Function: when a device wants to communicate with an IP outside its subnet, it sends the packet to the default gateway.
	the gateway routes the packet to th eappropriate destination.
	Configuration: the default gateway is typically the first IP address in the subnet (e.g., 192.168.1.1 for home networks).
	Why its Important? the default gateway connects local networks to external networks, enabling internet access and inter-subnet communication.

Note: default gateway is normaly the first IP

Overview of Loopback and APIPA:
	Loopback Address:
		The loopback address (127.0.0.1) is used for testing and troubleshooting network applications locally without needing a network connection.
		The entire 127.x.x.x range is reserved for loopback.
	APIPA (Automatic Private IP Addressing):
		When a device connot obtain an IP address form a DHCP server, it  automatically assigns itself an IP address in the range 168.254.x.x range. (between 169.254.0.1 and 168.254.255.254).
		This allows local communication within the network but prevents access to external networks.
	Why It's Important:
		Loopback is crucial for network diagnostics, while APIPA ensures devices can still communicate on a local network even when a DHCP server is unavailable.


CIDR(Classless Inter Domain Routing) is a method of IP address allocation and routing that allows more efficient use of IP addresses. Unlike traditional class based addressing, CIDR allocates IP addresses based on a network prefix rather than a fixed class (A, B, or C).

****Notation:**** a.b.c.d/n

- n = number of bits in the network prefix.
- Example: 192.168.1.0/24 first 24 bits are network, remaining 8 bits are host ID.

### Why CIDR?

Classful addressing wastes IP addresses:

|Class|IPs Available|Hosts|Example Wastage|
|---|---|---|---|
|A|2²⁴|2²⁴ - 2|Too large for small orgs|
|B|2¹⁶|2¹⁶ - 2|Wastes 49,150 hosts for 214 needed|
|C|2⁸|2⁸ - 2|Small networks only|

****Problem:**** Organizations often need a number of hosts that do not match class sizes, leading to wastage.  
****Solution:**** CIDR allows ****flexible block allocation**** matching exact requirements.

## Rules for Forming CIDR Blocks

- All IPs must be contiguous.
- Block size must be a power of 2 (2ⁿ) simplifies network division.
- First IP of block divisible by block size least significant bits of host ID should be 0.

All three rules are followed by this Block. Hence, it is a valid IP address block.

## Advantages of CIDR

- ****Efficient IP usage:**** Minimizes IPv4 address wastage.
- ****Flexible allocation:**** Supports networks of any size.
- ****Improved routing:**** Aggregates addresses for faster, simpler routing.
- ****Lower administrative overhead:**** Easier IP and network management.

## Disadvantages of CIDR

- ****Complexity****: CIDR is more complex to implement and manage compared to traditional class-based addressing.
- ****Compatibility Issues****: Some older network devices may not support CIDR.
- ****Security Concerns****: Implementing security measures like firewall rules and access control lists can be more difficult.

**Subnetting** is the procedure to divide the network into sub-networks or small networks, these smaller networks are known as subnets. The [subnet](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/) is also defined as an internal address made up of a combination of a small network and host segments. In a subnet, a few bits from the host portion are used to design small-sized subnetworks from the original network. In subnetting, network bits are converted into host bits. 

**Supernetting** is the procedure to combine small networks into larger spaces. In subnetting, Network addresses’ bits are increased. on the other hand, in supernetting, Host addresses’ bits are increased. Subnetting is implemented via Variable-length subnet masking, While super netting is implemented via Classless interdomain routing.

## **Difference between Subnetting and Supernetting**

| Subnetting                                                                                                                                          | Supernetting                                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Subnetting](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/) is the procedure to divide the network into sub-networks. | While [supernetting](https://www.geeksforgeeks.org/computer-networks/supernetting-in-network-layer/) is the procedure of combining small networks. |
| In subnetting, Network addresses' bits are increased.                                                                                               | While in supernetting, Host addresses' bits are increased.                                                                                         |
| In subnetting, The mask bits are moved towards the right.                                                                                           | While In supernetting, The mask bits are moved towards the left.                                                                                   |
| Subnetting is implemented via Variable-length subnet masking.                                                                                       | While supernetting is implemented via Classless interdomain routing.                                                                               |
| In subnetting, Address depletion is reduced or removed.                                                                                             | While It is used for simplifying the routing process.                                                                                              |


Overview of IPV6:
	Definition:
		IPv6 is the latest version of the internet protocol, designed to replace IPv4 die to address exhaustion.
		Uses 128-bit address, allowing for trillions of unique addresses.
	IPv6 Address Format:
		Written in hexadecimal and separated by colons. 
		Leading zeros can be omitted, and double colons represent consecutive zeros.
	Key Features of IPv6:
		Larger Address Space (2^128 addresses).
		Auto-configuration (no need for DHCP in many cases).
		No need for NAT (public addresses are abundant).
		Improved Security (built-in IPsec for encryption and authentication).
		Efficient Routing (smaller routing tables).


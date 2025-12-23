overview of CSMA/CD:
	definition: CSMA/CD (Carrier Sense Multiple Access/ Collision Detection) is a network access method used in Ethernet networks to detect and handle data collisions.
	How it Works:
		a device listens to the network before transmitting.
		if the medium is free, it sends the data.
		if a collision occurs, all devices stop transmitting and send a jam signal.
		devices wait for a random back off time before retrying.
	Why its important:
		Prevents excessive collisions in shared Ethernet environments.
		Ensures efficient use of bandwidth.
	Limitations:
		only effective in half-duplex Ethernet (not needed in full-duplex).
		performance degrades as network traffic increase.
		(Gemini add a diagram for this flow).

CSMA/CD flow:
	step 1: check if the sender is ready to transmit data packets.
	step 2: check if the transmit link is idle.
		the sender has to keep on checking if the transmission link/medium is idle.
		for this, it continuously senses transmission from other nodes.
		the sender sends dummy data on the link. if it does not receive any collision signal, this means the link is idle at the moment.
		if it senses that the carrier is free and there are no collisions, it sends the data. otherwise, it refrains from sending data.
	step 3:
		transmit the data & check for collisions.
		the sender transmits it s data on the link.
		CSMA/CD does not use an "acknowledgement" system. it checks for successful and unsuccessful transmission through collision signals.
		during transmission, if a collision signal is received by the node, transmission is stopped.
		the station then transmits a jam signal onto the link and waits for random time intervals it resends the frame.
		after some random time, it again attempts to transfer the data and repeats the above process.
	step 4:
		if no collision was detected in propagation, the sender completes its frame transmission and resets the counters.
### Advantages of CSMA/CD

- ****Efficient for Wired Networks**** : It works well in wired network like [Ethernet](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/) , as it is easier to detect both the Collision and response quickly, making it ideal and efficient for wired network.
- ****Reduces Collisions**** : It stops data transmission immediately as soon as they detect collision , reducing waste time and keep network efficient.
- ****Balances Network Traffic**** : CSMA/CD makes each device wait for random amount of time, after the collision is detected. This helps in preventing repeated collision and provides balance network traffic.
- ****Simple to Implement**** : It is easier to implement in wired environments, especially in networks where traffic is manageable and the chances of collision is also lower.

### Disadvantages of CSMA/CD

- ****Not Suitable for Wireless Networks**** : As it requires the ability to detect reliable collisions, so CSMA/CD will be difficult to implement in Wireless Network as these networks interfere with each other making collision detection ineffective.
- ****Adds Latency**** : As CSMA/CD waits for detecting collisions and waiting to retransmit after som some time, it can causes some delay leading to problems in some application where immediate response time is needed.
- ****Lower Efficiency in Busy Networks**** : As CSMA/CD waits for certain times to retransmit data after detecting collision. So in high traffic network frequent collisions can lead to delays and reduced efficiency
- ****Less Common in Today's Era:**** With the development of new technologies such as network switches and full duplex Ethernet , which helps in preventing collisions, it is becoming less common day by day in today's world.

overview of CSMA/CA:
	definition: CSMA/CA (Carrier Sense Multiple Access/ Collision Avoidance) is a network access method used in wireless networks to prevent data collisions before they occur.
	How it Works:
		a device listens to the channel before transmitting.
		if the channel is busy,, it waits and tries again later.
		Before sending, it may use RTS (Request to Send) and CTS (Clear to Send) to ensure the channel is free.
		Once clear,  is transmitted, and an ACK is received.
	Why it's Important:
		unlike wired networks, wireless devices cannot always detect collisions.
		Helps reduce the hidden node problem in Wi-Fi network.
	Limitations:
		Causes additional delays due to waiting mechanisms.
		Less effective than CSMA/CD on low-traffic networks.
	advantages of csma/ca:
		collision reduction - reduces the chances of collisions by checking whether network channel is free or not before sending data. this is useful in wireless networks where collision can interrupt communication.
		better for wireless networks - it is suitable for wireless system as it avoids collisions, by maintaining smoother connection.
		efficient channel use - the efficient use of channel means smoother communication occurs only when protocol checks whether channel is clear, reducing interruptions.
		energy efficient - it helps in saving energy efficiently as the protocol waits until the channel is clear to avoid unnecessary energy wastage.
	disadvantages of csma/ca:
		Lower Throughput: it can slow down the network due to additional overhead i.e., waiting for acknowledgment, leading to reduction of overall speed.
		Delay and Latency: CSMA/CA keeps constant check whether the channel is clear or not causing to delay. especially in network with high traffic. this makes it less effective for real time applications which needs quick response time.
		complex implementations: as compared to other simpler protocols, it requires more complex setup due to its acknowledgment and collision avoidance mechanisms.
		ineffective in high traffic: CSMA/CA wait time can be increased when many devices uses the same network, causing network slower and less efficient.

CSMA/CD was for wired networks and CSMA/CA is for wireless networks

Overview of Collision Domains:
	Definition: a collision domain is a network segment where data packets can collide when being transmitted simultaneously.
	How it Works:
		when multiple devices share the same transmission medium, data collisions can occur.
		in traditional hub-based Ethernet networks, all devices are in the same collision domain.
		switches create separate collision domains per port, reducing collisions.
	Ways to Reduce Collisions:
		using switches instead of hubs.
		implementing full-duplex Ethernet.
		Using VLANs to segment traffic.
	Common Issues in Large Collision Domains:
		network congestion due to excessive retransmissions.

- Hubs/repeaters = one large collision domain.
- Switches = separate collision domains.
- Routers = separate broadcast domains.
- Older devices have fewer ports and less control.

### ****.**** Collision Domain  

A ****Collision Domain**** is an area of a network where all devices share the same communication medium. When one device sends data, every other device in that domain must listen, even if the message isn’t for them. If two devices transmit at the same time, their data collides, forcing them to stop and resend later. This issue occurs only in ****half-duplex**** communication.

### Advantages:

- ****Higher Performance****: Fewer collisions mean less retransmission and faster data flow.
- ****Efficient Bandwidth Use:**** Each device or small group gets its own collision domain, reducing disruption.
- ****Better Stability****: Problems in one collision domain don’t impact others, improving overall network reliability.

### Disadvantages:

- ****Limited Scalability:**** Larger collision domains increase collisions, causing congestion and reduced performance.
- ****Difficult Management****: Frequent collisions make it harder to identify and troubleshoot network issues.
- ****Reduced Efficiency****: More retransmissions and congestion lead to overall poor network reliability and speed.

### 2. Broadcast Domain

A ****Broadcast Domain**** is a network area where any broadcast message sent by one device must be received by all others, which can lead to LAN congestion and reduced bandwidth. Therefore, increasing the number of both collision domains and broadcast domains helps improve network efficiency by isolating traffic and ensuring better bandwidth for all users.

### Advantages:

- ****Efficient Network Communication****: Supports protocols like ARP and DHCP that rely on sending messages to all devices at once.
- ****Simplified Network Management:**** Proper segmentation (e.g., VLANs) makes it easier to group devices and apply network policies.
- ****Improved Collaboration****: Allows devices within the same domain to easily discover and communicate with each other, supporting local network services..

### Disadvantages:

- ****More Congestion:**** Large broadcast domains create too much broadcast traffic, slowing the network and causing packet loss.
- ****Lower Security:**** All devices see broadcast packets, increasing risks like sniffing and ARP spoofing.
- ****Reduced Efficiency:**** Bigger broadcast domains waste bandwidth and hurt overall performance.

#### So, which of our network devices break collision domains, and which of them break broadcast domains? 

****HUB****

- A hub does ****not**** break collision domains or broadcast domains.
- All devices connected to a hub share ****one collision domain**** and ****one broadcast domain****.
- It doesn’t segment the network; it only connects devices.

****SWITCH****

- A switch ****breaks collision domains**** — each port is its own collision domain.
- This reduces collisions and improves performance.
- However, a switch does ****not**** break broadcast domains — all ports still share ****one broadcast domain****.

****ROUTER****

- A router breaks ****both collision domains and broadcast domains****.
- It separates networks completely, preventing broadcasts from crossing over.
- This makes routers essential for controlling traffic and improving network efficiency.

> Also, as repeaters and bridges differ from hubs and switches only in terms of the number of ports, a repeater does not break collision and broadcast domains, while a bridge breaks only collision domains.


Overview of Protocol Data Units (PDUs):
	Definition: a protocol data unit (PDU) is a formatted unit of data used as different layers of the OSI model.
	PDUs at Each OSI Layer:
		Layer 1 (Physical): Bits (raw data transmission)
		Layer 2 (Data Link): Frame (MAC addressing & error checking)
		Layer 3 (Network): Packet (IP addressing & routing)
		Layer 4 (Transport): Segment (TCP) / Datagram (UDP)
		Layer 5-7 (Session, Presentation, Application): Data
	Why it's important:
		helps standardize data exchange across network.
		enables encapsulation and de-encapsulation for efficient communication.
		supports error handling and reliable transmission.

The OSI model, which was first introduced by the **International Organization for Standardization (ISO) in 1977**, is a reference that specifies the transferring of data from one computer to another computer. The layered stack of the OSI (Open System Interconnection) reference model is made up of seven layers and each has a specific communication purpose to ensure reliable data flow between computers.

The goal of following the approach of the layered stack in the framework is to make network application and hardware development, management, and troubleshooting more specified and straightforward. Each layer is independent and self-contained so that it can carry out its communication tasks. The OSI model's application layer is at the top, while the physical layer is at the bottom as shown below.

### Protocol Data Unit (PDU)

Each layer's information is referred to as a Protocol Data Unit (PDU). Along with the data, it contains protocol-specific control information. Each layer will add (or delete) its protocol information as a PDU moves down (or up) each layer. The PDU is given a different name at each layer to represent its role. So, in a computer network, it refers to a block of information that is transferred between network end systems. As the name implies, it is used for [**Open System Interconnection (OSI)**](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/) model since it varies with layer-specific protocols and conventions. In a protocol stack, different layers have different types of data to be transferred. 

There are **seven layers** in the OSI Model as shown below and in the whole process of transferring information between these layers, only data goes through changes. Below mentioned are the **layers** of the OSI Model:

1. Physical Layer
2. Data Link Layer
3. Network Layer
4. Transport Layer
5. Session Layer
6. Presentation Layer
7. Application Layer

For example, in Layer 4, the PDU of the [**Transport Layer**](https://www.geeksforgeeks.org/computer-networks/transport-layer-responsibilities/) is referred to as a **segment** based on TCP (Transmission Control Protocol) and with **UDP** (User Datagram Protocol) PDU is referred to as a **datagram**. 

- Layer 3, the PDU of the **Network Layer** is referred to as a **packet**.
- Layer 2, the PDU of the **Data Link Layer** is referred to as **a frame**.
- Layer 1, the PDU of the Physical Layer is referred to as **bit** (1s or 0s).

_**Note:**_ Layer 5 and above, the PDU is referred to as data.
**For Internet Protocol Suite**

- The PDU of the **Transport Layer** is referred to as a **segment** based on TCP ([Transmission Control Protocol](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/)) and with UDP ([User Datagram Protocol](https://www.geeksforgeeks.org/computer-networks/user-datagram-protocol-udp/)) PDU is referred to as a **datagram**. 
- The PDU of the **Internet Layer** is referred to as a **packet**.
- The PDU of the **Link Layer** is referred to as a **frame**.

### Encapsulation of Protocol Data Unit (PDU):

When one PDU is wrapped inside another PDU then it is referred to as Encapsulation. It generally occurs when one protocol data unit (PDU) is transported inside the data field of the lower protocol data unit (PDU). In other words, a PDU contains data comprising relevant lower layer header information and is received from an upper network layer. This information has been prepared for transmission to the next lower layer in a row i.e. network layer. As data flows from one layer to the next, the PDU identifies its state. The major **difference** between **Protocol Data Unit (PDU)** and **Service Data Unit (SDU)** lies in the encapsulation as Service Data Units have not been able to encapsulate lower layer data transmission yet. 

The following table illustrates the PDU of each protocol stack layer.

| **Layer No.** | **Layer Name**     | **Description**                                                                                                                                                                                                                                                                                                                          |
| ------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Layer 1       | Physical Layer     | In this layer, PDU is **bits** (1s or 0s) for the transmission of data on the network.                                                                                                                                                                                                                                                   |
| Layer 2       | Data Link Layer    | In this layer, PDU comprises- <br><br>- Original data with TCP/UDP header<br>- Network layer header and <br>- Data Link Layer header contains MAC (Medium Access Control) addresses or physical addresses of sender and receiver. The trailer is also added to this layer.<br><br>PDU is called a **frame** in the Data Link Layer.      |
| Layer 3       | Network Layer      | In this layer, PDU comprises- <br><br>- Data with TCP/UDP headers<br>- The network layer header contains Logical Addresses or IP Addresses of the sender and receiver.<br><br>PDU is called a **packet** in Network Layer.                                                                                                               |
| Layer 4       | Transport Layer    | In this layer, PDU comprises- <br><br>- Data with TCP/UDP headers having sender’s and receiver’s TCP/UDP port numbers.<br><br>PDU is called **segment or datagram** in Transport Layer depending upon the protocol used. For TCP (connection-oriented protocol), it is segmented and for UDP (connectionless protocol) it is a datagram. |
| Layer 5       | Session Layer      | In this layer, PDU is data.                                                                                                                                                                                                                                                                                                              |
| Layer 6       | Presentation Layer | In this layer, PDU is data.                                                                                                                                                                                                                                                                                                              |
| Layer 7       | Application Layer  | In this layer, PDU contains original data made from a network application.                                                                                                                                                                                                                                                               |
**Cyclic Redundancy Check(CRC):** [Cyclic redundancy check](https://www.geeksforgeeks.org/dsa/modulo-2-binary-division/) is generally called an error detection mechanism because the special numbers are appended with a block of data so that the changes that are being detected with respect to any changes introduced in the storage.  
It is a more complex algorithm that is derived from simple CHECKSUM, MODULO ARITHMETIC, which is being treated out on each input word as it is a set of the coefficients for the polynomials.  
CRC is commonly used in digital networks and storage devices to detect accidental changes to raw data. If CRC generator is n bits, CRC is (n-1) bits. 

**CRC working condition:**

A CRC-enabled device calculates a short, fixed-length binary sequence, known as the check value or CRC, for each block of data to be sent or stored and appends it to the data, forming a code word. If the CRC values do not match, then the block contains a data error.

![](https://media.geeksforgeeks.org/wp-content/uploads/20211124230957/UntitledDiagram1-300x217.jpg)

CRC Working

**Example:** 

_Problem:_ Construct CRC message, let the divisor is 1101 and the data is 1011011. 

_Solution_: As the length of the divisor is 4, we have to add 4-1=3 zeros to the end of the word.  
Given data is 1011011 and CRC bits are 000 , i.e. 1011011000  {data + CRC received)

**Sender side:**

![](https://media.geeksforgeeks.org/wp-content/uploads/20211124231712/UntitledDiagram3-300x212.jpg)

Sender Side

So, the CRC, 001 is added to the message, 1011011.  
The transmitted message is 1011011001

**Receiver side:**

![](https://media.geeksforgeeks.org/wp-content/uploads/20211124231256/UntitledDiagram2-300x211.jpg)

Receiver Side

The above example, explains that the sender sends the data to the receiver without errors, and the receiver receives the correct data.  
Suppose if the receiver got a corrupted packet, the reminder will not get zero on the receiver side.

Overview of MTU (Maximum Transmission Unit):
	Definition: MTU is the largest size of a packet that can be transmitted over a network without fragmentation.
	Common MTU Values:
		Ethernet: 1500 bytes
		PPPoE: 1492 bytes
		IPv6: 1280 bytes (minimum required)
	Why MTU Matters:
		affects network performance and efficiency
		larger MTU reduces overhead but increases the impact of lost packets.
		smaller MTU increases overhead but minimizes retransmission delays.
	MTU and Fragmentation:
		if a packet is larger that the MTU, it is fragmented into smaller pieces.
		Path MTU Discovery (PMTUD) helps determine the best MTU dynamically.


The Maximum Transmission Unit (MTU) is the largest amount of data that can be transmitted in a single packet on a network. It is a parameter that is determined by the underlying network technology, and can be configured on network devices such as routers and switches.

The MTU is important because it determines the maximum size of data that can be transmitted across a network without fragmentation. If a packet is larger than the MTU, it is fragmented into smaller packets to be transmitted across the network, and then reassembled at the receiver. Fragmentation can result in additional processing overhead and increased network traffic, which can impact performance.

The MTU is typically specified in bytes, and can vary depending on the network technology being used. For example, Ethernet networks typically have an MTU of 1500 bytes, while some WAN technologies may have an MTU of 9000 bytes or higher.

In order to avoid fragmentation and ensure optimal network performance, it is important to ensure that the MTU is configured correctly on all devices on the network. This can be done through various means, such as adjusting the MTU settings on network interfaces or using technologies such as Path MTU Discovery to dynamically adjust the MTU based on the characteristics of the network path.

A maximum transmission unit also called as MTU, is a term used in networking and operating systems. It defines the largest size of the packet that can be transmitted as a single entity in a network connection. The size of the MTU dictates the amount of data that can be transmitted in bytes over a network.   
  
 ![[Pasted image 20251222140915.png]]


The larger MTU results in more data transmission during a single connection, therefore, reduces the overhead. On the other hand, the smaller MTU can be transferred faster, because of its size, thus reducing delay in the network. Therefore, the size of the MTU should be adjusted to optimize both the requirements.   
The default size of the maximum transmission unit is 1500 B, which is the Ethernet standard largest unit. 

#### Characteristics 

- Size of MTU is directly proportional to the amount of data transferred. Larger MTU size, larger chunk of data transmitted at once from the sender to the final recipient.
- MTU size is based on the specifications of the network administration.
- If size of MTU outweighs the capacity of router, it is re-transmitted again causing delay.
- It is the optimal packet size of the network.

#### Working of MTU

  
Let us suppose the Internet's Transmission Control Protocol(TCP) specified the size of MTU = 750 B, that is the maximum protocol data unit size that can be delivered from source to destination. In such a scenario, the following cases may arise: 

- If the system sends packets larger than the size of MTU, that is packet size > 750 B in this case, then the system packet will be fragmented to smaller packets such that their size doesn't exceed the largest packet size. The process of division of a large data packet into smaller chunks of data such that none of these chunks exceed the maximum frame size is called Fragmentation. These are later reassembled at the final client destination. 

![](https://media.geeksforgeeks.org/wp-content/uploads/20200427163903/Untitled-Diagram-130-1.jpg)

- If the system sends packets within MTU size, they are transmitted as a single frame in the network connection. However, packets much smaller than MTU may increase delay and cause network inefficiency. Reassembling packets in such a case is not required.   
     

![](https://media.geeksforgeeks.org/wp-content/uploads/20200427165705/Untitled-Diagram-510.jpg)

#### Applications

The maximum transmission unit has the following applications: 

- MTU is used over the internet, primarily by TCP to determine the optimal packet size.
- It is associated with Ethernet protocol, and is referred as protocol data unit(PDU).

**Issues in MTU (Maximum Transmission Unit) :**

There are several issues associated with the MTU (Maximum Transmission Unit) in computer networking:

1. Fragmentation: If a packet is larger than the MTU of a particular network segment, it needs to be fragmented into smaller packets to be transmitted across the network. This fragmentation can cause additional overhead and latency, which can impact network performance and reliability.
2. Path MTU Discovery: In some cases, the MTU can vary along the path between the sender and receiver. This can result in packets being dropped or delayed due to fragmentation, as the sender may not be aware of the correct MTU to use for each segment of the network path. Path MTU Discovery is a technique used to dynamically adjust the MTU based on the characteristics of the network path.
3. Jumbo Frames: Some network technologies support larger MTUs, known as jumbo frames. While this can improve network performance in certain scenarios, it can also introduce compatibility issues with devices that do not support jumbo frames.
4. Security: In some cases, attackers can exploit MTU-related vulnerabilities to launch denial-of-service attacks or to bypass network security measures such as firewalls.

- ****Path MTU Discovery (PMTUD):**** Path MTU Discovery is a mechanism used by TCP to dynamically decide the top-rated MSS value based totally at the MTU of the network path. When IPsec is used, PMTUD may also need to account for the additional overhead delivered by using IPsec encapsulation to make certain that packets aren't fragmented unnecessarily.

## What are jumbo frames?

A jumbo frame is an Ethernet frame, or data packet, with a payload greater than the standard size of 1,500 bytes. Jumbo frames are larger than the normal maximum transmission unit ([MTU](https://www.techtarget.com/searchnetworking/definition/maximum-transmission-unit)) established in the [Ethernet](https://www.techtarget.com/searchnetworking/definition/Ethernet) specification. In some circumstances, using jumbo frames can result in better performance, while in others it can lower performance.

In the Ethernet specifications, called IEEE [802.3,](https://www.techtarget.com/searchnetworking/definition/8023) it sets the normal maximum frame size at 1,518 or 1,522 bytes. This allows for 14 bytes of routing header data, 4 bytes of [checksum](https://www.techtarget.com/searchsecurity/definition/checksum) and 1,500 bytes of [payload](https://www.techtarget.com/searchsecurity/definition/payload) called the MTU. Because the standard set the frame size at 1,518 bytes, most devices are set by default to send and receive frames at this size.

In the time since the standard MTU for Ethernet was set, however, [network](https://www.techtarget.com/searchnetworking/definition/network) and processing have become much faster. [Gigabit Ethernet](https://www.techtarget.com/searchnetworking/definition/Gigabit-Ethernet) has largely become the norm, and even faster [10 Gigabit](https://www.techtarget.com/searchnetworking/definition/10-Gigabit-Ethernet) or even 40 Gigabit and [100 Gigabit](https://www.techtarget.com/searchnetworking/definition/100-Gigabit-Ethernet-100GbE) are used in special applications. On these faster networks there can be performance improvements if devices are configured to send larger data packets, called jumbo frames.

The most common jumbo frame is 9,000 bytes for the payload limit or MTU. While there is no specific standard, 9,000 bytes was chosen during the development of Gigabit Ethernet and was later adopted by most equipment vendors and agencies. Most modern Ethernet networking equipment will support 9,000-byte jumbo frames without difficulty.

A super jumbo frame is when the payload size is over 9,000 bytes. The theoretical maximum payload is 65,535 bytes, which is rarely used in practice. [IPv6](https://www.techtarget.com/searchnetworking/definition/IPv6-Internet-Protocol-Version-6) supports a jumbo payload or jumbogram option which allows for payloads up to about 4 gigabytes (GB).

Baby jumbo frames, or baby giant frames, are data frames only slightly larger than the standard maximum size of 1,522 bytes, typically up to 1,600 bytes. Baby jumbo frames are often used because certain network routing or encapsulation technologies require adding additional header information that would push a data packet over the standard frame size and cause packet fragmentation. For example, Multiprotocol Label Switching ([MPLS](https://www.techtarget.com/searchnetworking/definition/Multiprotocol-Label-Switching-MPLS)) adds 4 bytes as additional label information to each frame.

(Gemini explain why one might need jumbo frames)

Overview of ARP Table:
	Definition: the ARP table is a cache that stores mapping of IP addresses to MAC addresses in local network.
	How it Works:
		when a device wants to send data, it checks its ARP table to the destination MAC address.
		if the MAC address is not found, the device sends an ARP request
		the target device responds with and ARP reply, providing its MAC address.
		the mapping is stored in the ARP table for future use.
	Types of ARP Entries:
		Dynamic ARP Entries: learned automatically and expire after a certain time.
		Static ARP Entries: Manually configured and do not expire.

ARP (Address Resolution Protocol) is a network protocol used to determine the MAC address (hardware address) corresponding to an IP address.

- When one device in a LAN (Local Area Network) wants to communicate with another, it must know the destination’s MAC address.
- Since users and applications work with IP addresses, ARP acts as the translator, converting IP addresses into MAC addresses.

> ****Note:**** ARP works at the Network Layer (Layer 3) but interacts closely with the Data Link Layer (Layer 2). It was defined in RFC 826 (1982) and is still widely used with IPv4, Ethernet, Frame Relay, and ATM technologies.

## Important ARP Terms

- ****ARP Cache****: A table where resolved MAC addresses are stored for quick future use.
- ****ARP Cache Timeout****: The duration for which an entry remains valid in the ARP cache.
- ****ARP Request****: A broadcast message asking, "Who has this IP address?”
- ****ARP Reply/Response****: A unicast message containing the MAC address of the requested IP.

## Types of ARP

There are four main types of ARP, each used in different scenarios:

### 1. Proxy ARP

- Allows a proxy device (like a router) to respond to ARP requests on behalf of another device.
- Useful for hiding network complexity or connecting different subnets.

### 2. Gratuitous ARP

- A host sends an ARP request for its own IP address.
- Used to detect duplicate IP addresses and update ARP tables on other devices.

### 3. Reverse ARP (RARP)

- Used by a device to discover its own IP address when it only knows its MAC address.
- Example: Diskless computers at boot time request their IP from a server.

### 4. Inverse ARP (InARP)

- Opposite of ARP - used to discover the IP address from a known MAC address.
- Common in technologies like Frame Relay and ATM networks.

## How ARP Works

The working of ARP can be explained in the following steps:

![system_](https://media.geeksforgeeks.org/wp-content/uploads/20251010151409017059/system_.webp)

ARP Protocol

- ****Sender checks ARP Cache:**** If the MAC address for the destination IP is already cached, communication starts immediately.
- ****ARP Request Broadcast****: If not cached, the sender broadcasts an ARP request on the LAN.
- ****All Devices Receive Request****: Each device checks whether the requested IP matches its own.
- ****Destination Replies****: The device with the matching IP sends an ARP reply (unicast) containing its MAC address.
- ****Cache Update****: The sender updates its ARP cache with the new MAC address for future use.

## ARP Message Format

An ARP message consists of several fields:

![hardware_type](https://media.geeksforgeeks.org/wp-content/uploads/20251010151455296543/hardware_type.webp)

Message format of ARP

- ****Hardware Type (2 bytes):**** Defines hardware (Ethernet = 1).
- ****Protocol Type (2 bytes):**** Defines protocol (IPv4 = 0x0800).
- ****Hardware Address Length (1 byte):**** Length of MAC address (6 for Ethernet).
- ****Protocol Address Length (1 byte):**** Length of IP address (4 for IPv4).
- ****Operation Code (2 bytes):**** 1 for request, 2 for reply.
- ****Sender Hardware Address:**** MAC of the sender.
- ****Sender Protocol Address:**** IP of the sender.
- ****Target Hardware Address:**** Empty in request; receiver’s MAC in reply.
- ****Target Protocol Address:**** Receiver’s IP.

## Advantages of ARP Protocol

- ****Automatic Mapping:**** No need for manual configuration to resolve MAC addresses.
- ****Efficiency:**** Ensures smooth communication within LAN's.
- ****Transparency:**** Works in the background without user intervention.
- ****Flexibility:**** Supports different types (Proxy, Gratuitous, Reverse, Inverse) for varied networking needs.

based on the ARP request and ARP reply's on our request we can understand how many IP's reside on our network

Overview of Routing:
	Definition: routing is the process of forwarding data packets from one network to another using routers.
	Types to Routing:
		static Routing: manually configured routes that do not change automatically.
		Dynamic Routing: uses protocols to update routes automatically based on network conditions.
	Routing process:
		a packet arrives at a router.
		the router checks its routing table to find the best path.
		the packet is forwarded to the next hop towards its destination.
	Key Routing Components:
		routing table - a data base containing network paths.
		Next-hop address: the next router in the path.
		Metrics & administrative Distance: used to select the best routs.
		distance-vector: RIP, EIGRP
		linked-state: OSPF, IS-IS
		hybrid: BGP

- **Hop Count**: The number of network segments or devices a data packet traverses before reaching its destination.
-  **RIP (Routing Information Protocol)**: A routing protocol that utilizes hop count as a basic metric to determine the best routing path.

Enhanced Interior Gateway Routing Protocol (EIGRP) is an advanced distance-vector routing protocol that uses characteristics of both distance-vector and link-state protocols, making it a hybrid routing protocol. It operates at the Network Layer (Layer 3) of the OSI model and uses protocol number 88 for communication.

> ****Note:**** EIGRP helps routers or Layer 3 switches dynamically discover and maintain the best paths for forwarding packets within an Autonomous System (AS).

## Administrative Distance (AD) in EIGRP

Administrative Distance defines the trustworthiness of routing information. Lower AD values indicate higher trust. EIGRP assigns the following AD values:

|****EIGRP Routes****|****AD Value****|
|---|---|
|Summary Routes|5|
|Internal Routes|90|
|External Routes|170|

## Key EIGRP Messages

[EIGRP](https://www.geeksforgeeks.org/computer-networks/eigrp-configuration/) uses multiple message types for neighbor communication and routing updates. These messages can be multicast (224.0.0.10) or unicast, depending on the purpose:

1. ****Hello Message****: Used for neighbor discovery and keep-alives. Sent every 5 seconds (Hello timer). If no hello is received within 15 seconds (Dead timer), the neighbor is declared dead.
2. ****Full Update****: Sent after neighbor adjacency is formed. Contains all known best routes.
3. ****Partial Update****: Triggered by topology changes. Contains only the new or changed routes.
4. ****Query Message****: Sent when a destination is no longer reachable. Multicast to neighbors requesting alternative routes.
5. ****Reply Message****: Sent in response to a query. Provides alternate route information.
6. ****Acknowledgement Message****: A hello packet with no data, used to acknowledge updates, queries or replies.
7. ****NULL Update:**** Used for calculating timers like SRTT (Smooth Round Trip Time) and RTO (Retransmission Timeout).

> ****Note:**** Hello and Acknowledgement packets do not require acknowledgment. However, Query, Reply and Update messages are reliable and require acknowledgment.

## Composite Metric in EIGRP

EIGRP calculates its routing decision using a composite metric, which can include five variables:

- ****K1**** -> Bandwidth
- ****K2**** -> Load
- ****K3**** -> Delay
- ****K4**** -> Reliability
- ****K5**** -> MTU

> ****Note:**** By default, only K1 (bandwidth) and K3 (delay) are used. The default K values are (K1=1, K2=0, K3=1, K4=0, K5=0). This allows EIGRP to select the path with the lowest composite metric, ensuring efficient routing.

## Neighbor Adjacency Requirements

For two routers to form an EIGRP neighbor relationship, the following conditions must be satisfied:

- K values must match.
- Autonomous System (AS) number must be the same.
- Subnet mask must be identical.
- Authentication (if enabled) must match -> EIGRP supports MD5 authentication only.

## EIGRP Timers

EIGRP relies on timers for maintaining neighbor relationships:

- ****Hello Timer****: 5 seconds (interval between hello messages).
- ****Dead Timer (Hold Time)****: 15 seconds (neighbor declared dead if no hello received).

> ****Note:**** These timers ensure stable communication and quick detection of failures.

## Pros of EIGRP

- Fast convergence using the Diffusing Update Algorithm (DUAL).
- Supports VLSM and CIDR for efficient IP address usage.
- Efficient bandwidth usage with partial updates instead of full table exchanges.
- Scalability across large enterprise networks.
- Unequal-cost load balancing supported.


Overview of Routing Types:
	Definition: routing types define how network paths are determined and managed.
	Types of Routing:
		Static Routing: manually configured routes that do not change automatically.
		Dynamic Routing: uses protocols to update routes automatically based on network conditions.
	Routing Process:
		Static Routing: manually configured, does not chage automatically.
		Dynamic Routing: Uses protocols to update routs based on network conditions.
		Default Routing: a router forwards all unknown traffic to a predefined next-hop.
Feature - static routing - dynamic routing
configuration - manual - automated
adaptability - automatic changes - adapts to network changes
CPU usage - low - high
Scalability - Limited - high

Overview of Static Routing:
	Definition: static routing involves manually configuring routing entries in a router's routing table. routes do not change unless manually updated.
	How it Works:
		the network administrator manually specifies the destination network, the next-hop router, and other routing information.
		no automatic updates occur; changes are made manually.
	Characteristics:
		predictable & simple: easy to configure and maintain in small networks.
		Low CPU & Bandwidth Usage: since there are no dynamic updates.
		No Scalability: not suitable for large or frequently changing networks.

Overview of Dynamic Routing:
	Definition: routing protocols determine the best path for data packets between networks.
	Types of Routing protocols:
		Distance-Vector: Determines routes based on hop count (e.g., RIP, EIGRP).
		Link-State: Builds a complete network map for better path decisions (e.g., OSPF, IS-IS).
		Hybrid: Combines features of both types (e.g., BGP).
	Routing Protocol Operation:
		Routers exchange information about network topology.
		Best path selection based on protocol-specific metrics.
		Routing table updates dynamically as the network changes.
	Key Metrics Used in Routing Protocols:
		Hop Count: Number of routers a packet crosses.
		Bandwidth: Link speed affects route preference.
		Delay: Time taken to reach the destination.
		Cost/Administrative Distance: Determines route priority.
Feature, RIP, EIGRP
Primary Metric, Hop Count, multiple metrics (delay, bandwidth, reliability, load)
Max Hop Limit, 15 hops, 255 hops
complexity, very simple, moderately complex (but more flexible)
Vendor dependency, vendor-neutral (open standard), Cisco proprietary
convergence speed, slow, fast.


Link-State Routing Protocols:
	Link-State routing protocols build a complete network topology map to determine the best path.
	How it Works:
		each router builds a full network map using the shortest path first (SPF) algorithm.
		Routing tables are updated dynamically when network changs occur.
	Characteristics: 
		uses bandwidth, delay, and link cost as metrics (not just hop count).
		Faster convergence that distance-vector protocols.
		Less bandwidth usage due to triggered updates instead of periodic updates.
	Common Link-State Protocols:
		OSPF (open shortest path first): open standard protocol used in enterprise networks.
		IS-IS (intermediate system to intermediate system): udes on ISP and large-scale networks.
	
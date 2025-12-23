devices:

HUB:  
is a basic networking device that connects multiple computers is a LAN. it broadcasts incoming data to all connected devices, leading to network congestion and inefficiency. Hubs operate at the physical layer of the OSI model and are mostly replaced bu switches in modern networks.  
hubs broadcast the incoming data, meaning when pc1 gives it data to send to pc4, it gives it to all the pc's in the network.  
collision domain:  
the more the better. (Gemini add more information)

broadcast vs. multicast vs. unicast:  
broadcast sends data to all the network, multicast will send our data to the selected destinations, and unicast will only send data to the desired destination.  
Gemini add the information.

Bridge:  
a networking device that connects two or more network segments and filters traffic based on MAC addresses. it operates at the data link layer and reduces network congestion by forwarding traffic only when necessary. bridges are used to extend LAN's and improve network performance. OSI layer 2

Switch:  
a network device that connects multiple devices within a LAN and intelligently forwards data based on MAC addresses. unlike hubs, switches improve network efficiency by sending data only to the intended recipient. managed switches offer advanced features such as VLAN support,, QoS, and Port security. (Gemini explain VLAN, QoS, and port security)  
Switches work on level 2 and 3

Router:  
a networking device that forwards data packets between different networks. it connects local networks to the internet and directs traffic efficiently using IP addresses. Routers can provide additional functionalities such as NAT, DHCP, and security features. they are essential for enabling communication between different network segments.

Wireless Access Point (WAP):  
is a device that enables wireless devices to connect to a wired network. it extends network coverage and is commonly used in homes, offices, and public spaces. WAPs support Wi-Fi standards and can be standalone devices or integrated into routers

Firewall:  
a network security device that monitors and controls incoming and outgoing traffic based on predefined security rules. it acts as a barrier between a trusted internal network and untrusted external networks, such as the internet. firewalls can be hardware, software, or a combination of both and are essential for protecting against cyber threats.

Next-Generation Firewall (NGFW):  
an advanced security device that combines traditional firewall functions with additional features like deep packet inspection, application control, and intrusion prevention. NGFWs provide enhanced security by detecting and blocking sophisticated cyber threats.

Gemini add info on firewall vs. NGFW  
traditional firewalls are limited to level 4 but NGFWs can go all the way up to level 7.

Intrusion Detection System (IDS) & Intrusion Prevention System (IPS):  
are security technologies used to detect and prevent cyber threats. an IDS monitors network traffic for suspicious activity but does not take action, while an IPS actively blocks threats in real-time. both are essential for modern cyber security strategies.

Gemini add info on how IDS and IPS work in detail

Proxy Server:  
acts as an intermediary between a client (like your computer) and the internet. instead of connecting directly to a website, your device sends the request to the proxy, and the proxy forwards the request on your behalf.  
think of it like a personal assistant: you say, "hey, fetch this web page for me", and the proxy goes, gets it, and hands it back to you.

purpose - Description  
Privacy - hides you real IP address from the destination.  
Access Control - Network admins can block or allow access to certain websites.  
Caching - saves commonly accessed web pages to improve speed and reduce bandwidth.  
monitoring - tracks and logs user activity for security and policy enforcement.  
Bypass Restrictions - can help users access blocked or region-limited content.

Load balancer:  
a network device or software solution tha distributes incoming traffic acrerss multiple backend servers, ensuring no silgle server is overwhelmed and system performance remains optional.  
benefit - description  
traffic distribution - spreds the load acress multiple servers to avoid overload.  
high availability - if one server fails, others take over.  
scalability - easy to add or remove servers as needed.  
faster response - requests go to the fastest or least busy server.

common load balancing algorithms:  
round robin - distributes requests sequentially  
least connections - sends to the server with the fewest active session.  
ip hash - chooses server based on users ip address

packer shaper:  
or traffic shaper is a network device or software that analyzes, controls, and prioritizes network traffic. its goal is to optimize bandwidth usage and ensure that critical applications (like VoIP or video calls) run smoothly even user heavy load

benefit - description  
improves key app performance - ensures VoIP, confrencing, or internal tools get needed badwidth  
prevents like congestion - stops large downloads or streaming form hogging the connection  
enforces user policies - limits users or groups by speed, time, or service  
enables QoS strategies - supports high-quality performance and user eperience
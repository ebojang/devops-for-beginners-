
Networking- is the practice of connecting computers and other devices together so they can share information, resources and access the internet.

**Local Area Network (LAN)**- is a network that connects devices within small local area such as home, office and school.
They are fast and secure due to their limited range.

**Wide Area Network (WAN)-** connect devices across large geographical areas, such as cities, countries and continents. example of WAN is the internet.
WANs often use public infrastructure (like telephone lines, satellites, a VPN over the internet) and are typically slower than LANs due to distance and scale.

**How WAN connects multiple LANs**
Every LAN is connected to a router> Routers in point A & B are connected via WAN links (fibre optic cables, satelites links, cellular networks and the internet) > arrive at destination router and enters target LAN. 
The data travels **from LAN → router → WAN → router → LAN**.

==IMPORTANCE OF NETWORKING IN DEVOPS== 
 * enables communication between servers and applications
 * critical for launching and updating applications 
 * crucial in monitoring and managing infrastructure
 * enhances troubleshooting, performance and scalability

==Key Networking Components:==
**Switches** - connects devices within the same LAN and allow them to communicate effectively.
it uses MAC addresses to forward data.
**Routers**- is a layer 3 device connects different networks together. eg home LAN to the internet.
router assigns IP addresses to devices on your network
it decides the best path for data travel.
**Firewalls** - protects networks from unauthorised access. They monitor and control incoming and outgoing networks. firewalls can be physical device (often in routers) or software (windows firewall).

**IP ADRESS** - is a unique identifier for devices on a network.
two types:
==IP4== -  are 32 bit numbers &  ==IPV6== - are 128 bits numbers 

**Media Access Control (MAC Address)**
Is a unique identifier assigned to a network interface.
It's a 48 bit address and it operates at a data link layer (layer2)
it facilitates identification within a local network.

**PORTS & PROTOCOLS** 
Ports are essentially doors within your actual device. Each port number is used for a specific type of network communication. Eg. Http: port 80 | https: port 443 
ports are logical endpoints for communication.

**TCP PROTOCOL**
TCP is a connection orientated and it requires handshake for connection to be established.
it is reliable for data transfer.
it checks for error in data and control the flow of data to prevent congestion.
example, web browsing, emails and file transfer 

**USER DATAGRAM PROTOCOL (UDP)**
UDP - is simple to send and receive data 
udp is fast
no prior communication is required 
UDP is unreliable and each package is sent independently, no error checking or flow control 
==use cases for udp:==
video streaming, vpn and online gaming 





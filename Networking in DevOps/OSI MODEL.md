7 LAYERS
==Please Do Not Throw Sausage Pizza Away== 

Layer 7- **Application** -  provides network services directly to applications. components are : Http. smtp, ftp etc. 

Layer 6 - **Presentation** - ensures data is in usable format. it encrypts data and aid in data formatting. convert jpeg into a real format

Layer 5 - **Session** - it establishes, maintain and terminate connections between applications.
components of L5, authentication 

Layer 4 - **Transport** - is responsible for reliable data transfer to the upper layers. it enables data to arrive in the right sequence. it promotes end-end connections.  protocols of L4 are TCP and UDP

Layer 3 - **Network** - manages packet forwarding including routing through intermediate routers. 
it determines the path data is transferred to different networks. components of L3 are routers and IP addresses 

Layer 2 - **Data link** - put your data into frames (envelopes) and ensures data is transferred correctly between adjacent network nodes. components of data link layer are MAC addresses , switched & Bridges.

Layer 1 - **Physical** : transmits raw bit stream over a physical medium such as fibre, cables and NIC


==**OSI MODEL SENDERS END : STEP-BY-STEP**== 
user types in google.com or facebook.com
1) **Application layer**- browser created a http request- this is application data
2) **Presentation layer**- data is encoded/serialized: if HTTPS, TLS encrypts the HTTP data. data is then encrypted
3) **Session layer** - is where session management happens (it's job is to start, manage and end conversation. it is where authentication, keeping state)
4) **Transport layer** - TCP (usually) breaks the data into **segments**, adds a T**CP header (source/destination** **ports**) this header tells the receiver which application (port) should get the data and how to reassemble it.
5) **Network layer** - this is where ip address is assigned. The ***IP header adds source and destination ip addresses.***
6) **Data link layer**- the ip packet is wrapped in an **ethernet frame**. Ethernet header adds source and destination MAC addresses. **ARP (address resolution protocol)** might be used to map ip address to a mac address.
7) **Physical layer**- frame bits are converted into electrical /radio signals over the cable or air


**RECEIVER: STEP-BY-STEP**
1) Physical layer- NIC receives signal and converts to bits
2) Data link layer- matches MAC address or destination MAC address and move frame upwards
3) Network layer- checks ip header (destination ip address) and moves upward
4) Transport layer - reads the TCP header: it checks the destination port, reassemble segments, sends ACKs for received data.  Once segment is complete, it strips the TCP header.
5) Session layer- use session info to maintain session,
6) Presentation layer - decrypts data. example convert jpeg - image 
7) Application layer- Deliver the final HTTP response to the browser process that requested it.







TCP/ IP MODEL LAYERS 

**APPLICATION LAYER** > http, tls , dns etc 
**Transport Layer** > tcp, udp
**INTERNET LAYER** > IP addresses and routing 
**NETWORK ACCESS LAYER** >it's comination of physical and data li nk layer  Ethernet, wireless LAN 

Transmission Control Protocol
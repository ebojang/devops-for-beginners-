
subnetting is dividing a network into smaller networks.
it improves network management and efficiency.

CIDR
classless inter domain routing - isa method for writing ip address and their network size.
is essential for allocating Ip addresses and routing ip packets.
it combines ip adress- the networks starting point and subnet mask- written as a /
slash (/)- tells you how many bits are used for network.
format: ip address/prefix_length 192.63.1.0/24 
/24 is the network address and the remaining 8 bits is the host address.

Subnet Mask helps defines network and host portions
How to convert binary to a decimal?

10110= 22   1011=  11
start counting from right to left in ^2 = 1 2 4 8 16 32 64 etc and add the values under the ones 

FIND THE BUMBER OF SUBNETS & THE NUMBER OF VALID HOSTS PER SUBNET
SUBNET: 2^# of subnet bits in subnet mask

Valid Hosts: 2^# of host bits  -2 
we -2 because of the network number and broadcast address which does not get assign to the host .
valid host adress means : the number of ip addresses we can assign to an endpoint (computer or router).

ip address 192.168.1.0

255.255.255.240 (//28)
11111111.11111111.11111111.11110000     class c network 
subnets= 2^(32-8) i.e 2^4=16  subnet=16
Hosts= 2^4= 16-2=14 hosts=14

NETWORK ADDRESS TRANSLATION (NAT)
NAT converts private ip address to a public ip address.
it facilitates communication between internal network and the internet.

HOW NAT WORKS 

- At home, your devices have **private IP addresses** (e.g., 192.168.1.5).
- When a device wants to access the internet, it sends data to your **router**.
- **The router uses NAT** to replace your private IP with **one public IP** (the one given by your internet provider).
- When websites reply, the router **translates** the public IP back to the correct private IP inside your network.

NAT IS USEFUL:
- **Saves IP addresses** (many devices share one public IP)    
- **Adds security** (hides your private network from the outside).
- **Allows internal devices** to access the internet.

STATIC NAT- maps a single private ip address to a single public ip address.
dynamic NAT- maps a private i address to a one of many public ip addresses

Port Address Translation (PAT) - allows multiple devices on a local network to be mapped to a single public ip address but with different port numbers.
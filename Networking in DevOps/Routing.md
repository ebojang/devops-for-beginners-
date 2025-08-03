
Routing is the process of determining  the best route for data to travel across networks.
It ensures data reaches its destination efficiently.

**how routing works?**
Routers determine the best path by using the routing table to make decisions.

Routing ensures network performance optimization and ensures reliable application delivery.

**STATIC & DYNAMIC ROUTING** 

STATIC ROUTING- is where routes are manually setup by network admin. 
The routes/path are fixed and do not change.
it is simple but **not scalable.

DYNAMIC ROUTING -  automatically adjust route/ path based on current network conditions. 
dynamic routing uses routing protocols to find the best path. They are scalable and adjustable.

Routing protocols uses algorithms that determine best paths for data to travel across networks.
They automate route updates and improve network resilience.

==Common routing protocols:==
OSPF- open shortest path- finds the shortest path for data to travel. Each router knows the **entire network topology** (link-state).
OSPF is an internal gateway protocol.
it's used inside one organisation 

Border Gateway Protocol (BGP)- Is used to **connect different organizations/networks across the Internet**. it focuses on **policy** and **reachability**, not speed.
BGP - is an external gateway protocol.
example of BGP
Your ISP uses BGP to tell your router how to reach Google's or Amazon's networks.

Understanding CIDR (Classless Inter-Domain Routing)
CIDR (Classless Inter-Domain Routing) is a method for allocating and identifying IP address ranges more efficiently than the old class-based system. A CIDR notation consists of an IP address followed by a slash and a number.
The smaller the number after the slash, the **larger the range** of IPs covered. CIDR is widely used in networking, especially for configuring VPCs and security groups in cloud platforms like AWS.


Private IP ADDRESSES
**private networks**, which are used within homes, organizations, or internal systems — and are **not routable on the public internet**.
The main **private IP ranges** are:
- `10.0.0.0` to `10.255.255.255`
- `172.16.0.0` to `172.31.255.255`
- `192.168.0.0` to `192.168.255.255`
Note:
Additionally, `127.0.0.1` is reserved as the **loopback address** used for testing network configurations locally.
It does not need an external network connection. 

PUBLIC IP ADDRESSESS
**public IP addresses**  are **accessible over the internet** and must be globally unique.


VIRTUAL PRIVATE CLOUD (VPC)
**VPC (Virtual Private Cloud)** in AWS is your own **isolated private network** within the AWS cloud.
You can create multiple VPCs in each AWS region (default limit: **5 per region**, but this can be increased).

Each VPC has an **IP range** defined using **CIDR notation**:
- **Smallest range:** `/28` → 16 IP addresses
- **Largest range:** `/16` → 65,536 IP addresses


Understanding Subnets in a VPC (IPv4)
A **subnet** is a smaller network inside your **VPC (Virtual Private Cloud)**. It allows you to divide your VPC into multiple sections.

Subnets can be:
- **Public:** Have internet access (through an Internet Gateway).
- **Private:** No direct internet access.

AWS reserves 5 IP addresses in every subnet — these cannot be used by your instances. For example, in `10.0.0.0/24`:

- `.0` – Network address
- `.1` – AWS VPC router
- `.2` – Amazon DNS server
- `.3` – Reserved for future use
- `.255` – Broadcast address (not supported, but reserved)
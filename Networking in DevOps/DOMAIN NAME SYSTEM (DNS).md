
DNS- translate domain names into ip address. It is essential for accessing websites.

**DNS COMPONENTS**
==Name servers;==
name servers load DNS settings and configurations. they can be authoritative or recursive:
Authoritative name servers: holds the actual dns records. when queried they provide the definite answers such as the ip address of the domain name.

**HOW TO FIND WHICH NAME SERVER A WEBSITE IS HOSTED ON?**
run:
dig ns google.com  or dig +short ns google.com

**what is zone files?**
Zone files are stores inside name servers and they store information about the domain. they help name servers answer queries about how to get to domain if name server doesn't know answer directly.

A & AAAA Records
A RECORD > maps domain to ipv4 address
AAAA Record > maps domain to ipv6 address

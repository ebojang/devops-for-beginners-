
DNS- translate domain names into ip address. It is essential for accessing websites.

**DNS COMPONENTS**
==Name servers;==
name servers load DNS settings and configurations. they can be authoritative or recursive:
**Authoritative name servers**: holds the actual dns records. when queried they provide the definite answers such as the ip address of the domain name.

**HOW TO FIND WHICH NAME SERVER A WEBSITE IS HOSTED ON?**
run:
dig ns google.com  or dig +short ns google.com

**what is zone files?**
Zone files are stores inside name servers and they store information about the domain. they help name servers answer queries about how to get to domain if name server doesn't know answer directly.

**A & AAAA Records**
A RECORD > maps domain to ipv4 address
AAAA Record > maps domain to ipv6 address

DNS RESOLUTION -  is the process of converting domain names into ip addresses.

**DNS RESOLUTION PROCESS**
1) Google.com in a browser 
2) DNS resolver- first make a query of google.com by checking its local cache to check for ip address. if no resolve found, resolver then queries the root server.
3) Root server-  go to the name server for .com TLD server (top level domain server).
4) Top level domain server (TLD server) checks with the authoritative name server.
5) the dns resolver then queries the right authoritative server for google.com
6) Authoritative Name server: then sends the ip address of google.com to the DNS resolver 
7) dns resolver then send the ip address back to the web browser.
8) the web browser then connects to the web server at example 142.250.180.14


**==*DNS TOOLS FOR DEBUGGING*==** 

**ns lookup**: is a tool for querying dns servers. it gives you information about the queried site domain.
 run:  nslookup (domain name example google.com)
 nslookup google.com
 
==**Break down of the result for nslookup google.com**== 

eboja@EbrimaBojang:~$ nslookup google.com
==Server:         10.255.255.254== (this is your local router/server, the server you going through to get to your destination site)
Address:        10.255.255.254==#53==(#53 specifies the port number for dns)

**Non-authoritative answer:** (this means the response came back from a cache and NOT directly form an authoritative DNS server for google.com )
Name:   google.com
==Address: 142.250.179.238==( this is the ip address to get to google.com)
Name:   google.com
Address: 2a00:1450:4009:81d::200e

**Dig: is an advanced dns query tool.** 
dig google.com

**==BREAKDOWN OF RESULT FOR dig google.com==**
dig is more detaild. it has question and answer section:

; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
**==;; QUESTION SECTION:==**
;google.com.                    IN      A  (THIS SHOWS YOU THE QUERY YOU MADE eg google.com)
**==;; ANSWER SECTION:==**
google.com.             111     IN      A       **==142.250.179.238==**( on the answer section, the ip address is the address associated with that domain)

;; Query time: 29 msec
;; SERVER: 10.255.255.254#53(10.255.255.254) (UDP)
;; WHEN: Fri Aug 01 17:28:53 BST 2025
;; MSG SIZE  rcvd: 55
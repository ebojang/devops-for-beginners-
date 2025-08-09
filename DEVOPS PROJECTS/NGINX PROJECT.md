
Aim of the project 

- Run a website (NGINX web server) on an Azure Virtual machine (VM)
    
- Map a domain example (bojang.uk) to my vm server using Cloudflare
    
- Access the web page through the web browser using your domain


## 🛠️ Step-by-Step Instructions with Explanations

1) Go to azure portal> Virtual machine and create vm 
2) Configure vm (subscription, resource group, region, image (ubuntu server 22.04), standard B1 size, authentication (SSH), Inbound port rules , 22 for ssh connection and port 80 for http or website connection).
3) create and wait for VM to deply. 
4) once deployed, connect to vm via ssh. 
5) use azure cli > az login and connect to your account 

TO INSTALL & configure  NGINX on VM
note: NGINX is a web server software 
1) open bash in azure cli and run: 
2) sudo apt update 
3) sudo apt install nginx  -y 
4) sudo systemctl start nginx
5) sudo systemctl enable nginx 
6) to test that it is ruinning, run ( curl http://localhost)

Create an A record and point domain (nginx.bojang.uk) to VM public IP

Disabled proxying to allow direct routing and transparent flow to our server.
![[Screenshot 2025-08-07 233038.png]]

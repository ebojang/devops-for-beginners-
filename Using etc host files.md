using /etc/host files  on our local machine 

**what is /etc/hosts?**
This is a local file on your computer that maps domain names to ip addresses.
it allows you to overwrite DNS settings for certain domain names by providing alternative ip address.

when you first type in a domain name in your browser, your computer first checks the etc/host file.
if the domain is listed in the /etc/host file, it uses the provided ip address instead of querying the DNS server. This can be used for testing, development and debugging

How to edit a Host File?
open the file with a text editor  such as vscode or vim
admin privilege is required to edit the file example sudo vim /etc/hosts
* add entry in this format: ip_address domain_name  example 127.1.1.12 example.com
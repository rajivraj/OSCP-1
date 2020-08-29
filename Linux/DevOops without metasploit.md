DevOops without metasploit

![DevOops](https://user-images.githubusercontent.com/55708909/91637910-52af4b80-ea29-11ea-8ccf-dfc3e2057e85.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA DevOops -p- 10.10.10.91

![DevOops_nmap](https://user-images.githubusercontent.com/55708909/91637969-c4879500-ea29-11ea-9b3d-4a1f4a49e93b.png)

Nothing special about port 5000 but upload directory looks interesting

![DevOops_port_5000](https://user-images.githubusercontent.com/55708909/91638025-2a741c80-ea2a-11ea-98bd-a93b8dc2558b.png)

I knew we can put a payload inside xml file and get execute and then with the help of burp we can get various files.

Grab the ssh key and quickly log into the system.

![DevOops_burp_1](https://user-images.githubusercontent.com/55708909/91638180-1bda3500-ea2b-11ea-864c-20d31eac81dd.png)

![DevOops_burp_2](https://user-images.githubusercontent.com/55708909/91638194-285e8d80-ea2b-11ea-8aff-d61994f93d9b.png)





Arctic without metasploit

![Arctic](https://user-images.githubusercontent.com/55708909/91928522-e9b22700-ecf9-11ea-8e4f-c0b58d72e18e.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Arctic -p- 10.10.10.11

![Arctic_nmap](https://user-images.githubusercontent.com/55708909/91930680-1ddc1680-ecff-11ea-9147-2e2564c46c1d.png)

At port 8500 i saw some directory and after digging deeper i saw administrator 

![Arctic_port_85](https://user-images.githubusercontent.com/55708909/91930674-1ae12600-ecff-11ea-94d3-5a86cfec6e69.png)

![Arctic_admin](https://user-images.githubusercontent.com/55708909/91930685-20d70700-ecff-11ea-9377-9d772de281a1.png)

Admin page is asking for password lets see if there is some way to bypass this 

![arctic_admin](https://user-images.githubusercontent.com/55708909/91931428-0e5dcd00-ed01-11ea-9abf-4539a3f5358a.png)

![Arctic_exploit](https://user-images.githubusercontent.com/55708909/91931450-17e73500-ed01-11ea-91a7-7807d6b1f486.png)

Use directory traversal exploit 14641.py

from that change the url address as per your need i.e. 

http://10.10.10.11:8500/CFIDE/administrator/enter.cfm?locale=../../../../../../../../../../ColdFusion8/lib/password.properties%00en

![Arctic_hash](https://user-images.githubusercontent.com/55708909/91931760-f76baa80-ed01-11ea-8a9c-100ef4a511e1.png)

![Arctic_hash_crack](https://user-images.githubusercontent.com/55708909/91931757-f5a1e700-ed01-11ea-90e7-e98d147e661a.png)

Login in with password as happyday

![Arctic_admin_login](https://user-images.githubusercontent.com/55708909/91932261-4a922d00-ed03-11ea-9797-fc67b1772270.png)


I was looking for plugin where i can write malicious script or upload a file and get it executed from web server and i found schedule task plugin.

![Arctic_shell](https://user-images.githubusercontent.com/55708909/91933198-f9376d00-ed05-11ea-81db-21be83bdfc9f.png)

![Arctic_shell_con](https://user-images.githubusercontent.com/55708909/91933193-f5a3e600-ed05-11ea-8b1d-ba6bfd5f433d.png)

Grab user.txt and for root.txt i did systeminfo

![Arctis_user](https://user-images.githubusercontent.com/55708909/91933452-837fd100-ed06-11ea-9afd-5ee6b979b78e.png)

![Arctic_root_1](https://user-images.githubusercontent.com/55708909/91936478-90ec8980-ed0d-11ea-98e9-4a54e0465dfd.png)

Arctic without metasploit

![Arctic](https://user-images.githubusercontent.com/55708909/91928522-e9b22700-ecf9-11ea-8e4f-c0b58d72e18e.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Arctic -p- 10.10.10.11

![Arctic_nmap](https://user-images.githubusercontent.com/55708909/91930680-1ddc1680-ecff-11ea-9147-2e2564c46c1d.png)

At port 8500 i saw some directory and after digging deeper i saw administrator 

![Arctic_port_85](https://user-images.githubusercontent.com/55708909/91930674-1ae12600-ecff-11ea-94d3-5a86cfec6e69.png)

![Arctic_admin](https://user-images.githubusercontent.com/55708909/91930685-20d70700-ecff-11ea-9377-9d772de281a1.png)

Admin page is asking for password lets see if there is some way to bypass this 

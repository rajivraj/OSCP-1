Jerry without metasploit

![Jerry](https://user-images.githubusercontent.com/55708909/91583665-2a631680-e96f-11ea-8965-2fd133a841ef.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Jerry -p- 10.10.10.95



As we have only one port to enumerate i will roger that 
.
Port 8080 seems to have directory manager/html

it will ask for credentials first cut the login panel and there you will fing login credentials and after that loging in with credentials tomcat:s3cret

![Jerry_login](https://user-images.githubusercontent.com/55708909/91584367-284d8780-e970-11ea-8c08-f8103b9584a2.png)


Netmon without metasploit

![Netmon](https://user-images.githubusercontent.com/55708909/91636135-d4987800-ea1b-11ea-902f-2f9d5f0ff6d7.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Netmon -p- 10.10.10.152

![Netmon_nmap](https://user-images.githubusercontent.com/55708909/91636167-28a35c80-ea1c-11ea-935e-bb8e3ca8d87b.png)

Logged into FTP server and from there grab user.txt
 
Now moving to web server.

![Netmon_port_80](https://user-images.githubusercontent.com/55708909/91636230-a5ced180-ea1c-11ea-900a-cc7f9cef994f.png)

Didn't find anything strange on web server and i google about credential and it gave me login credentials location

![Netmon_PRTG](https://user-images.githubusercontent.com/55708909/91636295-0e1db300-ea1d-11ea-91b4-9c9f1b66900d.png)

Log into FTP SERVER and grab the credentials.

![Netmon_password](https://user-images.githubusercontent.com/55708909/91636387-b16ec800-ea1d-11ea-95c1-9bbbb3afbfdf.png)

For priviledge escalation searchsploit has a exploit

![Netmon_PRTG_EXPLOIT](https://user-images.githubusercontent.com/55708909/91636430-0579ac80-ea1e-11ea-8a2b-947a210291f4.png)

Use the exploit to gain root priviledges



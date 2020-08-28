Sense without metasploit

![Sense](https://user-images.githubusercontent.com/55708909/91535131-501cfb00-e930-11ea-89a7-5941a56fc649.png)


Starting with nmap scan :

Nmap -sC -sV -T4 -A -O -oA Sense -p- 10.10.10.60

![Sense_nmap](https://user-images.githubusercontent.com/55708909/91535378-aee27480-e930-11ea-8d72-59229acb99c4.png)

Port 80 gave me login page

![Sense_port_80](https://user-images.githubusercontent.com/55708909/91535640-16002900-e931-11ea-8cb1-102cee2e6b5d.png)

Ran hydra and bang i am blocked then ran gobuster but found nothing interesting as i learned from friendzone to quickly move to other port and so i did.

Port 443 gave me two interesting directory 

1- Changelog.txt
2- system-users.txt

![Sense_change](https://user-images.githubusercontent.com/55708909/91538838-10f1a880-e936-11ea-9b8f-075639b01142.png)

![Sense_user](https://user-images.githubusercontent.com/55708909/91539110-734aa900-e936-11ea-8bee-0a2f56435362.png)

Login in with credentials usernam: rohit & password: pfsense

Version 2.1.3 and look for proper exploit

![Sense_exploit](https://user-images.githubusercontent.com/55708909/91542219-1e5d6180-e93b-11ea-888e-e06dd940253c.png)

Fire up the exploit and we will get the shell

![Sense_shell](https://user-images.githubusercontent.com/55708909/91542347-582e6800-e93b-11ea-9daa-12c53d83e174.png)

We will get root priviledges

![Sense_root](https://user-images.githubusercontent.com/55708909/91542643-ca06b180-e93b-11ea-98ea-bac52e8cbd64.png)


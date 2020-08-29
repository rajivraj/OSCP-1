Active without metasploit:

![Active](https://user-images.githubusercontent.com/55708909/91635434-23431380-ea16-11ea-9260-80fdb6f88210.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Active -p- 10.10.10.100

![Active_nmap](https://user-images.githubusercontent.com/55708909/91635498-9b113e00-ea16-11ea-9204-dc545920bc13.png)

Let's start with smb 

![Active_smb_1](https://user-images.githubusercontent.com/55708909/91635755-b8470c00-ea18-11ea-9f02-10b7b5c8d8df.png)

![Active_smb_2](https://user-images.githubusercontent.com/55708909/91635761-bf6e1a00-ea18-11ea-9d66-4f720c44fa1c.png)

Grab the username and password for it 

active.htb\SVC_TGS : GPPstillStandingStrong2k18

Now login through smb and Grab user.txt

![Active_user_txt](https://user-images.githubusercontent.com/55708909/91635872-9c903580-ea19-11ea-9a3a-e00e9c3c9e0e.png)





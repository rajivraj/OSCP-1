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

Now since we do have kerberos i am going to use impacket:getusersSPN.PY and grab the hashes and use that to have password for psexec.py

![Active_hashes](https://user-images.githubusercontent.com/55708909/91635985-9484c580-ea1a-11ea-92da-70e7419d7420.png)

Use hashcat or john the ripper and we have password: Ticketmaster1968

Now use psexec.py 

python psexec.py administrator:Ticketmaster1968@10.10.10.100

And Now have desirable access.

![Active_root](https://user-images.githubusercontent.com/55708909/91636044-373d4400-ea1b-11ea-9853-3625d0026720.png)


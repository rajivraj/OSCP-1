Brainfuck without metasploit

![Brainfuck](https://user-images.githubusercontent.com/55708909/91796691-77c8d780-ec3e-11ea-8d94-f68ebcbc94d0.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Brainfuck -p- 10.10.10.17

![Brainfuck_nmap](https://user-images.githubusercontent.com/55708909/91796807-b78fbf00-ec3e-11ea-80b9-8905a6fa85a9.png)

As usual i first visited port 443 and its just a normal website with nginx running anyways 

From nmap result i saw a domain so quick i try dns enumeration and found potential domain.

![Brainfuck_port_80](https://user-images.githubusercontent.com/55708909/91797038-384ebb00-ec3f-11ea-9c5b-a81fce7ba049.png)

![Brainfuck_wpscan](https://user-images.githubusercontent.com/55708909/91797030-338a0700-ec3f-11ea-8d25-8356424f9780.png)

This could be our potential attack vector i search on searchsploit and found one too.

![Brainfuck_exploit](https://user-images.githubusercontent.com/55708909/91797256-be6b0180-ec3f-11ea-9b31-9bb18827bf6f.png)

Save the html elements in a file called bypass.html and change the url action="http://wp/wp-admin/admin-ajax.php" to action="http://brainfuck.htb/wp-admin/admin-ajax.php" and for username value run wpsacn with enumerate commands you
will find two names administrator and admin try both of them and see if you can find something interesting.

After that you will be sign in as admin just look at source code and find out the credentials.

Then quickly set up mail server and within no time you will have orestis credentials

![Brainfuck_mail](https://user-images.githubusercontent.com/55708909/91798359-5669ea80-ec42-11ea-9baf-1595c0aa7273.png)

Login in to secret form with valid credentials obtained earlier and you will be have this welcome page

![Brainfuck_secret](https://user-images.githubusercontent.com/55708909/91798757-3c7cd780-ec43-11ea-8ef0-5f33700c3254.png)


If we look at it we will get to know that orestis has is asking for ssh key and for that he open another private thread 

When we go to key thread we see some jargon and at the end of each statement this is statement 

This is a cipher text :

PieagnmJkoijeg nbw zwx mle grwsnn

OrestisHackingforfunandprofit

![Brainfuck_ssh](https://user-images.githubusercontent.com/55708909/91804141-ddba5c80-ec48-11ea-851a-fab50acbc686.png)

![Brainfuck_password](https://user-images.githubusercontent.com/55708909/91804365-edd23c00-ec48-11ea-936f-d90039ea01c2.png)

Let me tell you what's happening here first we get was cipher text from there we get the key value

using that key value we decrypt url and get id_rsa private key in order to use we need password so using
this tool wget https://raw.githubusercontent.com/openwall/john/bleeding-jumbo/run/ssh2john.py
 we first convert it into john format and then use jtr to crack the password.
 
 
 For root access go through decrypt.txt and encrypt.stage you will find a strings i just through a buch of code and then find a possible script to decode decrypt.txt and output.txt , for p, q, e value put them from decrypt.txt and for ct value put them from output.txt and you will get root flag
 
 ![Brainfuck_root](https://user-images.githubusercontent.com/55708909/91811150-ab126300-ec4c-11ea-9276-d03c38d535e3.png)

 

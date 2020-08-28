Irked without metasploit

![Irked](https://user-images.githubusercontent.com/55708909/91524945-15aa6280-e91e-11ea-9f23-b378ed53b458.png)


Starting with nmap scan:
 
Nmap -sC -sV -T4 -A -O -oA Irked -p- 10.10.10.117

![Irked_namp](https://user-images.githubusercontent.com/55708909/91526560-8c952a80-e921-11ea-87f5-e372297b9508.png)

By solving so many boxes i have built a strong methodology under which i always run nmap script for reverse shell for that a particular services and in this

case i was promising and i got a reverse shell.

![Irked_shell](https://user-images.githubusercontent.com/55708909/91525557-653d5e00-e91f-11ea-82f4-2f692b35f6ca.png)

I uploaded linenum.sh and found suspicious files called viewuser when i look inside it it was running another script so i though to replace it with my own 

version.

![Irked_root](https://user-images.githubusercontent.com/55708909/91526070-75097200-e920-11ea-861f-ba57016669df.png)






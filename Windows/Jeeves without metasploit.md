Jeeves without metasploit

![Jeeves](https://user-images.githubusercontent.com/55708909/91626861-45b23e00-e9d0-11ea-9ed9-bb7927eeca59.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Jeeves -p- 10.10.10.63

![Jeeves_nmap](https://user-images.githubusercontent.com/55708909/91626976-6202aa80-e9d1-11ea-88fb-bd4ce9ca1566.png)

Now after going through so many boxes i have developed my own methodology to go after web server i.e. Port 80 and 50000

At port 80 this is what i saw first:

![Jeeves_port_80](https://user-images.githubusercontent.com/55708909/91627048-fc62ee00-e9d1-11ea-97ed-9fa4c26dd8a4.png)

After directory brute forcing, looking at source code and search on searchsploit and googling it i didn't find anything interesting so i moved on to port 50000

![Jeeves_port_50000](https://user-images.githubusercontent.com/55708909/91627086-624f7580-e9d2-11ea-9cdb-7473a68232e4.png)

I did a directory bruteforce and found ask-jeeves which give me a dashboard for various plugins, earlier while doing enumeration i saw same page and i knew this could be a potential attack vector

![Jeeves_ask_jeeves](https://user-images.githubusercontent.com/55708909/91627152-f7526e80-e9d2-11ea-8720-0e13ead030db.png)

As i told you i read about how to exploit this vector so i knew it. I click on MANAGE-JENKINS then to SCRIPT-CONSOLE and you will see some kind of IDE stuff . At top you will see GROVY SCRIPT. Google something like grovy script reveres shell and you will have a script for reverse shell.

![Jeeves_script_console](https://user-images.githubusercontent.com/55708909/91627252-cde61280-e9d3-11ea-9f61-d916aad67ab4.png)

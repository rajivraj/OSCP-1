Solidstate without metasploit:

![Solidstate](https://user-images.githubusercontent.com/55708909/91543637-3386c000-e93c-11ea-80cf-fd6103e59d01.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Solidstate -p- 10.10.10.51


Visited port 80 but didn't found anything it was a rabbit hole


![Solidstate_port_80](https://user-images.githubusercontent.com/55708909/91545511-c3c60480-e93e-11ea-9823-d360f4e1e742.png)

Let's move to port 4555 and search for something promising

![Solidstate_port_4555](https://user-images.githubusercontent.com/55708909/91545769-215a5100-e93f-11ea-8de2-b35a8fda7946.png)


Let's look at python exploit.

It seems to first login as root with password root then make a user called as 

../../../../../../../../etc/bash_completion.d

Then send the payload through SMTP huh.

![Solidstate_exploit](https://user-images.githubusercontent.com/55708909/91546142-a180b680-e93f-11ea-9df4-e833cf7b7b74.png)

Let's use netcat and telnet



Solidstate without metasploit:

![Solidstate](https://user-images.githubusercontent.com/55708909/91543637-3386c000-e93c-11ea-80cf-fd6103e59d01.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Solidstate -p- 10.10.10.51

![Solidstate_nmap](https://user-images.githubusercontent.com/55708909/91546796-a72acc00-e940-11ea-8d3b-aa3e90977f0c.png)

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

I use netcat to change password for mindy and then use telnet for accessing her SMTP ACCOUNT . Got ssh password.

![Solidstate_nc](https://user-images.githubusercontent.com/55708909/91548710-6b453600-e943-11ea-83a7-fa23c1e2439e.png)

Priviledge escalation:

For this we first add user 

../../../../../../../../etc/bash_completion.d

After that we login in to smtp through telnet and then send a payload and ssh into mindy and got the connection back

![Solidstate_user](https://user-images.githubusercontent.com/55708909/91551691-3c7d8e80-e948-11ea-9cb3-7d73e231b5cd.png)

For root change the tmp.py files with our malicious ones and got the root

Goodbye





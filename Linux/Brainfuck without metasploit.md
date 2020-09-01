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

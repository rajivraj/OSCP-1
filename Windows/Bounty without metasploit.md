Bounty without metasploit

![Bounty](https://user-images.githubusercontent.com/55708909/91937841-71a32b80-ed10-11ea-9fcd-60ef1af791ef.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Bounty -p- 10.10.10.93


When i visited to port 80 i found just a random wizard pic

![Bounty_port_80](https://user-images.githubusercontent.com/55708909/91938354-803e1280-ed11-11ea-90f5-e275964e513c.png)

After that i did directory brute forcing and found many stuff but one seems promising transfer.aspx 

I uploaded a png file and can see it on the web

![Bounty_pic](https://user-images.githubusercontent.com/55708909/91938925-8254a100-ed12-11ea-8f89-b55fbec64a68.png)

saw it seems to work i try to upload reverse shell in various format aspx ,asp and php but fail.

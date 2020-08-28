Valentine without metasploit:

![Valentine](https://user-images.githubusercontent.com/55708909/91554925-a9475780-e94d-11ea-8695-12abd15e7fd2.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Valentine -p- 10.10.10.79

![Valentine_nmap](https://user-images.githubusercontent.com/55708909/91555169-21158200-e94e-11ea-8464-18c6c35cce92.png)

Let's start enumerating port 80

Both port seems dead end so i fire up gobuster and found something interesting.

![Valentine_port_80](https://user-images.githubusercontent.com/55708909/91555489-bd3f8900-e94e-11ea-8123-647e2726141c.png)

![Valentine_port_443](https://user-images.githubusercontent.com/55708909/91555506-c2043d00-e94e-11ea-86c8-96b858f140e2.png)

Find ssh key in hex format change it into ASCII FORMAT AND YOU WILL HAVE SSH KEY

![Valentine_dev](https://user-images.githubusercontent.com/55708909/91555870-6b4b3300-e94f-11ea-99ed-19f30c74b58a.png)

![Valentine_dev1](https://user-images.githubusercontent.com/55708909/91555865-6a1a0600-e94f-11ea-9378-ab705bbe5bef.png)

It's asking for password moving on earlier i find that this system has heartbleed vulnerability and i exactly know 

proper exploit for it in python version.

git clone https://gist.github.com/10174134.git

Run the script and you will get password in base64 encoding , decode and then use ssh key to login in.

Here it is encoded password base64

After login i look for suspicious thing and found tmux was running as root and so i run it and got root



![Valentine_heart](https://user-images.githubusercontent.com/55708909/91557114-8454e380-e951-11ea-8c74-19e3d8a1c5cb.png)


Here it is the decoded password

![Valentine_decode](https://user-images.githubusercontent.com/55708909/91557227-bbc39000-e951-11ea-9fe0-7755abef2749.png)

For root i run tmux and got root

![Valentine_root](https://user-images.githubusercontent.com/55708909/91557742-b155c600-e952-11ea-9fc0-9d6f1272b5be.png)




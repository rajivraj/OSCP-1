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



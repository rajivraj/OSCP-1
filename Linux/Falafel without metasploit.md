Falafel without metasploit

![Falafel](https://user-images.githubusercontent.com/55708909/91638625-6c06c680-ea2e-11ea-8ec3-61aed8cc2b05.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Falafel -p- 10.10.10.73

![Falafel_nmap](https://user-images.githubusercontent.com/55708909/91638710-0e26ae80-ea2f-11ea-87f6-0da1d278ab6e.png)

Port 80 just have normal greetings page and then after that i find cyberlaw.txt with some notes

![Falafel_port_80](https://user-images.githubusercontent.com/55708909/91638891-42e73580-ea30-11ea-831a-06404fd10556.png)

For this box i am going to use sqlmap as i haven't touched it till now

![Falafel_sqlmap](https://user-images.githubusercontent.com/55708909/91638910-6c07c600-ea30-11ea-80a1-1a91593cb5e7.png)

Type something like magic hashes starting with 0 and you will get the password if no then try this whitehatsec.com

![Falafel_magic](https://user-images.githubusercontent.com/55708909/91638974-ee908580-ea30-11ea-9d6d-113f6fc70679.png)

login into the page the first thing i tried is uploading php script but failed anyways then i look here and there and find
this

![Falafel_limit](https://user-images.githubusercontent.com/55708909/91639034-4b8c3b80-ea31-11ea-8aa1-05531be66fc6.png)

With the help of ippsec. i got to know how to get ahead



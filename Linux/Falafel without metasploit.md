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

For getting the shell i divided the steps in 4 stages:

Stage1 - Send file with 255 character in gif format, the web server will shorten the file name to 236 this means there is restriction

![Falafel_hack_1](https://user-images.githubusercontent.com/55708909/91651215-96489a80-eaa7-11ea-9295-a4cd61ee6947.png)

Stage2 - After that i modify the file with .php.gif extension in such a format 234.php.gif this means that file name till 233 counts then from 234 to 236 it is .php and then after that .gif what this will do is it will bypass the gif format requirements and will be uploaded on web server

![Falafel_hack_2](https://user-images.githubusercontent.com/55708909/91651218-9d6fa880-eaa7-11ea-8bb6-a5cbbf5b72b4.png)

Step3  - After that look at source code and figure out where the file is stored i means the directory location and execute the file 

![Falafel_hack_3](https://user-images.githubusercontent.com/55708909/91651221-a496b680-eaa7-11ea-9d24-5c6e40289743.png)

Step4 - Grab the shell using burp and with the help of netcat you will get a reverse shell

![Falafel_shell](https://user-images.githubusercontent.com/55708909/91651366-92b61300-eaa9-11ea-9b5b-2f4d9597d8d7.png)

![Falafel_user_txt](https://user-images.githubusercontent.com/55708909/91651370-9a75b780-eaa9-11ea-93d0-b81f8a404a34.png)




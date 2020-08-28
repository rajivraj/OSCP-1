Granny without metasploit

![Granny](https://user-images.githubusercontent.com/55708909/91565422-cf75f300-e95f-11ea-90cf-8c513413cb59.png)


Starting with nmap scan :

Nmap -sC -sV -T4 -A -O -oA Granny -p- 10.10.10.15

![Granny_nmap](https://user-images.githubusercontent.com/55708909/91565889-84a8ab00-e960-11ea-9390-d0ff4e1d5010.png)

![Granny_port_80](https://user-images.githubusercontent.com/55708909/91566563-8030c200-e961-11ea-9e2d-7d1166fcb58d.png)

As soon as i saw so many HTTP METHODS i quickly fire up davtest and see what ways i can find to crack the boxes.

![Granny_davtest](https://user-images.githubusercontent.com/55708909/91566826-d69e0080-e961-11ea-91a7-5cd5583975d4.png)

So we can't get a shell using asp or aspx format but txt and html are allowed

From previous nmap result we can see that PUT and MOVE methods are allowed. Straightaway coming to point by using put method i am gonna put shell in txt format and using move method i am gonna change the extension from txt to aspx and we will have our reverse shell.

As you can see i have uploaded a html page on website and now i am gonna change the extension from html to aspx

![Granny_stage_1](https://user-images.githubusercontent.com/55708909/91568313-fd106b80-e962-11ea-8fbc-a02869609f19.png)

I was able to change the extension from html to aspx

![Granny_stage_2](https://user-images.githubusercontent.com/55708909/91569805-858f0c00-e963-11ea-8e2c-b22ca72aa321.png)

Now what i am going to do is i am gonna create a reverse shell using msfvenom in aspx format, change it into txt and then using curl i am gonna move from txt to aspx and will execute and get a reverse shell.

![Granny_shell](https://user-images.githubusercontent.com/55708909/91578784-4d3dfc80-e968-11ea-8f27-93d132e33bdc.png)


For Priviledge escalation i run systeminfo then use windows-exploit-suugester which recommended me to run churrasco kernel exploit and therefore so i did and got Highest priviledge BAM.

![Granny_root](https://user-images.githubusercontent.com/55708909/91579342-187e7500-e969-11ea-8999-d0aedd391050.png)



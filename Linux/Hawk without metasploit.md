Hawk without metasploit

![Hawk](https://user-images.githubusercontent.com/55708909/91636974-6d31f680-ea22-11ea-94f9-4f51fc2b7fc8.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Hawk -p- 10.10.10.102

![Hawk_nmap_1](https://user-images.githubusercontent.com/55708909/91637065-1e389100-ea23-11ea-9b89-dac64183d2f8.png)

![Hawk_nmap_2](https://user-images.githubusercontent.com/55708909/91637069-27c1f900-ea23-11ea-90bf-4783862638fe.png)

As i logged into ftp i found .drupal.txt.enc get it and i use brute forcer and it gave me some password

![Hawk_ftp](https://user-images.githubusercontent.com/55708909/91637165-0281ba80-ea24-11ea-9e7a-9233d42a6985.png)

![Hawk_brute](https://user-images.githubusercontent.com/55708909/91637169-0d3c4f80-ea24-11ea-8032-25ff8953300b.png)

Now i move to port 80 and found login page i used the credentials and got inside it. 

I google for possible exploitation and found that it can be possible through contents plugin and php script

yup that's what i needed. But before that you need to enable php extensions.

Now just write php code and run it and you will have a connection.

For root i use 45506.py exploit suggested by searchsploit and it gave me root acces

Transfer the script to target box in tmp directory and run the command and then you will have root access

![Irked_root](https://user-images.githubusercontent.com/55708909/91637761-5e4e4280-ea28-11ea-947e-afdbc47739fc.png)




Nineveh without metasploit

![Nineveh](https://user-images.githubusercontent.com/55708909/91530779-5360b880-e929-11ea-88ce-497793e843e5.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Nineveh -p- 10.10.10.43

![Nineveh_nmap](https://user-images.githubusercontent.com/55708909/91531003-b2263200-e929-11ea-8050-2492f2cfc34b.png)

When i visited port 80 it was just a normal page doesn't seems promising and the i ran gobuster and found out departmental panel to login 

![Nineveh_department](https://user-images.githubusercontent.com/55708909/91531425-6922ad80-e92a-11ea-942d-f52485affdc9.png)

![Nineveh_user](https://user-images.githubusercontent.com/55708909/91531469-78096000-e92a-11ea-9c51-a9bf6900e1e4.png)

ran john to brute force with admin as user and password: 1q2w3e4r5t

Found a page and after url with Notes parameter seems LFI &  after going to and fro i found way 

![NIneveh_LFI](https://user-images.githubusercontent.com/55708909/91531898-26150a00-e92b-11ea-98d8-b6687b73ecba.png)


http://10.10.10.43/department/manage.php?notes=/ninevehNotes/../../../../etc/passwd

After that i use burp to see if i could go deeeper but found nothing interesting moving on.

AT port 443 Simple pic so i quickly fire up dirbuster and found db and ran hydra and found password :password123

![Nineveh_db](https://user-images.githubusercontent.com/55708909/91532469-fc101780-e92b-11ea-9d26-dcd7221c6bf0.png)

![Nineveh_phplite](https://user-images.githubusercontent.com/55708909/91532559-1fd35d80-e92c-11ea-8020-5e7ca4b6056a.png)

![Nineveh_search](https://user-images.githubusercontent.com/55708909/91532936-aab45800-e92c-11ea-8211-f328af227600.png)

As per this exploit we have to first create a database with malicious code .php and through previous LFI we can execute the php file and get shell

![Nineveh_VAR](https://user-images.githubusercontent.com/55708909/91533635-d3891d00-e92d-11ea-854d-eef88231c26f.png)

We got execution, Now through it in burp and get reverse shell




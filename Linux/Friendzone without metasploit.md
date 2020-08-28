Friendzone without metasploit:

![Friendzone](https://user-images.githubusercontent.com/55708909/91519627-c7db2d80-e910-11ea-8cd8-572f641e48e0.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Friendzone -p- 10.10.10.123

![Friendzone_nmap](https://user-images.githubusercontent.com/55708909/91519805-3e782b00-e911-11ea-8eda-06b3870f82dc.png)

As soon as i visit port 80 i found dns and one from nmap result so i quickly check for potential dns and look what i found.

![Friendzone_dns](https://user-images.githubusercontent.com/55708909/91520019-e0981300-e911-11ea-849c-eec8b6bb16e1.png)

Let's visit all of them one by one to find out something interesting.

![Friendzone_admin](https://user-images.githubusercontent.com/55708909/91520525-20abc580-e913-11ea-9301-534b1dcbfe49.png)

I tried the normal credential but couldn't get in and brute force take huge time so i moved to port 139 and found something interesting.

![Friendzone_smb](https://user-images.githubusercontent.com/55708909/91520684-85672000-e913-11ea-9823-05e256ee24c3.png)

![Friendzone_creds](https://user-images.githubusercontent.com/55708909/91522085-f6f49d80-e916-11ea-892a-0e2aa0598c9d.png)

I found the credentials for admin panel quickly login in and it recommended me to visit dashboard.php when i visited it agai it 

recommended me to put image_id=a.jpg&pagename=timestamp and when in inserted it i got this one therefore in replaced timestamp with 

number and got and image. Seems some php script is running backened.










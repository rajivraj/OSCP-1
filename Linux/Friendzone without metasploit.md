Friendzone without metasploit:

![Friendzone](https://user-images.githubusercontent.com/55708909/91519627-c7db2d80-e910-11ea-8cd8-572f641e48e0.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Friendzone -p- 10.10.10.123

![Friendzone_nmap](https://user-images.githubusercontent.com/55708909/91519805-3e782b00-e911-11ea-8eda-06b3870f82dc.png)

As soon as i visit port 80 i found dns and one from nmap result so i quickly check for potential dns and look what i found.

![Friendzone_dns](https://user-images.githubusercontent.com/55708909/91520019-e0981300-e911-11ea-849c-eec8b6bb16e1.png)

Let's visit all of them one by one to find out something interesting.







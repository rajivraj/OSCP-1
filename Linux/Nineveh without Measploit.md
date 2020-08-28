Nineveh without metasploit

![Nineveh](https://user-images.githubusercontent.com/55708909/91530779-5360b880-e929-11ea-88ce-497793e843e5.png)


Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Nineveh -p- 10.10.10.43

![Nineveh_nmap](https://user-images.githubusercontent.com/55708909/91531003-b2263200-e929-11ea-8050-2492f2cfc34b.png)

When i visited port 80 it was just a normal page doesn't seems promising and the i ran gobuster and found out departmental panel to login 

![Nineveh_department](https://user-images.githubusercontent.com/55708909/91531425-6922ad80-e92a-11ea-942d-f52485affdc9.png)

![Nineveh_user](https://user-images.githubusercontent.com/55708909/91531469-78096000-e92a-11ea-9c51-a9bf6900e1e4.png)


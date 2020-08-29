Lacasadepapel without metasploit

![Lacasa](https://user-images.githubusercontent.com/55708909/91628482-c3c91180-e9dd-11ea-84fe-8b50974c2241.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Lacasa -p- 10.10.10.131

![Lacasa_nmap](https://user-images.githubusercontent.com/55708909/91628523-2d492000-e9de-11ea-9655-a39daca4d6df.png)

As always i will start with port 80.

![Lacasa_port_80](https://user-images.githubusercontent.com/55708909/91628586-c5470980-e9de-11ea-88fa-0440396a0801.png)

Did the usual directory brute force, source-code and other stuff but didn't find anything useful so i will move to port 443

![Lacasa_port_443](https://user-images.githubusercontent.com/55708909/91628624-2e2e8180-e9df-11ea-8feb-542878e9a6c7.png)

It's asking for client certificate so let's generate one.

For that we need key also let's see from which service we can get.

For the key i exploited ftp service and get PSY SHELL

From there i got the ca.key. Now we have the ca.key and ca.crt it's gonna be messy so i shall start

![Lacasa_ca_key](https://user-images.githubusercontent.com/55708909/91628869-81093880-e9e1-11ea-85cf-9177f3816c68.png)

![Lacasa_ca_key1](https://user-images.githubusercontent.com/55708909/91628868-7e0e4800-e9e1-11ea-98db-2d7cc57a59fd.png)













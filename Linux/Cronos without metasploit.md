Cronos without metasploit:

![Cronos](https://user-images.githubusercontent.com/55708909/91448621-bd308200-e897-11ea-8983-8835a9c47ec7.png)

Starting with nmap scan:

Nmap -sC -sv -T4 -A -O -oA Cronos -p- 10.10.10.13

![Cronos_nmap](https://user-images.githubusercontent.com/55708909/91449090-5069b780-e898-11ea-861b-ed8c54de2ee0.png)

Enumerating port 53 with nslookup and host we get various attack vector and find one juicy one admin.cronos.htb

![Cronos_dns](https://user-images.githubusercontent.com/55708909/91450122-91ae9700-e899-11ea-9f92-b42ba7c9ab51.png)

Exploited it using payload : admin'#  & we are in .

![Cronos_admin](https://user-images.githubusercontent.com/55708909/91450307-c7538000-e899-11ea-915d-a7ae89dcf6d3.png)

![Cronos_code_execution](https://user-images.githubusercontent.com/55708909/91451522-21087a00-e89b-11ea-8f7f-47bb38f3b69e.png)

Now we are going to upload a reverse shell using nc. The payload should be URL encoded CTRL + U and then send it and we will get

reverse shell.








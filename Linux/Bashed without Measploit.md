Bashed without metasploit

![Bashed](https://user-images.githubusercontent.com/55708909/91441132-4e4e2b80-e88d-11ea-91d0-74722f609997.png)


Starting with Nmap scan:

Nmap -sC -sV -T4 -A -O -oA Bashed -p- 10.10.10.68

![Bashed_nmap](https://user-images.githubusercontent.com/55708909/91441304-9bca9880-e88d-11ea-8737-e852e6ae7026.png)

Since we have only one port to enumerate

![Bashed_port_80](https://user-images.githubusercontent.com/55708909/91441460-de8c7080-e88d-11ea-8823-1f8a204190da.png)

I ran gobuster and find interesting files one of them is dev which further contain some more juicy files

![Bashed_gobuster](https://user-images.githubusercontent.com/55708909/91441929-af2a3380-e88e-11ea-8eda-da06d7f72f88.png)

![Bashed_devd](https://user-images.githubusercontent.com/55708909/91441976-c406c700-e88e-11ea-8df6-4410b33317f4.png)

As soon as i click on phpbash.php i get a shell on the box 

![Bashed_shell](https://user-images.githubusercontent.com/55708909/91442376-60c96480-e88f-11ea-904a-8dd5294eef01.png)

![Bashed_flag_1](https://user-images.githubusercontent.com/55708909/91442744-f2d16d00-e88f-11ea-8573-b07afe19a6a6.png)















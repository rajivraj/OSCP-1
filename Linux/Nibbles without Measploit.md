Nibbles without metasploit

![Nibbles](https://user-images.githubusercontent.com/55708909/91443972-b69f0c00-e891-11ea-8542-ce1344adf0b9.png)


Starting with nmap:

Nmap -sC -sV -T4 -A -O -oA Nibbles -p- 10.10.10.75

![Nibbles_nmap](https://user-images.githubusercontent.com/55708909/91444243-172e4900-e892-11ea-9202-c1ea07dc12b4.png)

When i started enumerating port 80 in the source code i saw directory name /nibbleblog/ i look into it and found it that it is 
powered by Nibbleblog

![Nibbles_port_80](https://user-images.githubusercontent.com/55708909/91444616-a20f4380-e892-11ea-9400-25fc8c94d3cd.png)
 
Ran gobuster and found out admin.php and login in with admin:nibbles

Earlier with gobuster we found out its version number 4.0.3

![Nibbles_admin](https://user-images.githubusercontent.com/55708909/91445499-d1728000-e893-11ea-9959-9897dfeea027.png)


Found out the vulnerability by googling and yup here we are .

https://wikihak.com/how-to-upload-a-shell-in-nibbleblog-4-0-3/

As per this go into plugins and then into my-image ==configure and the upload image.php with reverse shell code and execute it

http://localhost/nibbleblog/content/private/plugins/my_image/image.php  

We will get a reverse shell.










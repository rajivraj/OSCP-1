For Windows Priviledge Escalation guide you can follow these two posts:


1-https://www.fuzzysecurity.com/tutorials/16.html


2-https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/

Scripts which are helpful in escalating Priviledges are:

1- WinPEAS

wget https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/winPEAS/winPEASbat/winPEAS.bat

wget https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/blob/master/winPEAS/winPEASexe/winPEAS/obj/x64/Release/winPEAS.exe

2- Sherlock 

wget https://raw.githubusercontent.com/rasta-mouse/Sherlock/master/Sherlock.ps1

3- Watson 

git clone https://github.com/rasta-mouse/Watson.git

4- JAWS

git clone https://github.com/411Hall/JAWS.git

5- Windows exploit suggester

git clone https://github.com/AonCyberLabs/Windows-Exploit-Suggester.git

HERE'S HOW I APPROACH FOR ESCALATING PRIVILEDGES:

1- Default Credentials - Run winpeas to look for juicy files with short duration of time

2- DLL Hijacking   

3- Unquoted service path

4- Weak File Permissions

5- Weak Service Permissions

6- Weak Registry Permissions

7- Always Installed Elevated

8- Modify Autorun files

9- Potato Attacks

10-Kernel exploits (git clone https://github.com/abatchy17/WindowsExploits.git)





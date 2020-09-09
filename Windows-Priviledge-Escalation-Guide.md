For Windows Priviledge Escalation guide you can follow these two posts:


1-https://www.fuzzysecurity.com/tutorials/16.html


2-https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/


HERE'S HOW I APPROACH FOR ESCALATING PRIVILEDGES:

1- Default Credentials - Run winpeas to look for juicy files with short duration of time

2- DLL Hijacking   

3- Unquoted service path

![Windows_priv_esc_unquoted_service](https://user-images.githubusercontent.com/55708909/92546523-63a15d80-f270-11ea-8589-3159509e9cf7.png)

![Windows_priv_esc_unquoted_service_1](https://user-images.githubusercontent.com/55708909/92546966-6f415400-f271-11ea-8727-9bd01310211a.png)


4- Weak File Permissions

5- Weak Service Permissions

6- Weak Registry Permissions

7- Always Installed Elevated

![Windows_priv_esc_installed_elevated](https://user-images.githubusercontent.com/55708909/92548628-28555d80-f275-11ea-8a89-d0e79e07fe91.png)


8- Modify Autorun files

![Windows_priv_esc_autorun](https://user-images.githubusercontent.com/55708909/92547994-8e40e580-f273-11ea-847b-915dfcc1d238.png)


9- Potato Attacks

10-Kernel exploits (git clone https://github.com/abatchy17/WindowsExploits.git)





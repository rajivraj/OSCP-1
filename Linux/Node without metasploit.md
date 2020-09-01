Node without metasploit

![Node](https://user-images.githubusercontent.com/55708909/91813657-a6e84480-ec50-11ea-80a6-55c24e948821.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Node -p- 10.10.10.58

![Node_nmap](https://user-images.githubusercontent.com/55708909/91813981-1827f780-ec51-11ea-81ff-9b9195a50902.png)

When i visited port 3000 then i saw a welcome page and when i look at the source code i saw some juicy things

![Node_port_3000](https://user-images.githubusercontent.com/55708909/91822070-e153e080-ec54-11ea-88cb-e6d46101b3f3.png)

![Node_source_code](https://user-images.githubusercontent.com/55708909/91822060-dd27c300-ec54-11ea-9699-aefa0049c70a.png)

When i went through different url i saw a page without admin credentials and one with valid credentials

![Node_admin_1](https://user-images.githubusercontent.com/55708909/91822271-224bf500-ec55-11ea-90d9-fb4dadfeb83e.png)

![Node_admin_2](https://user-images.githubusercontent.com/55708909/91822267-20823180-ec55-11ea-865c-48eb392ea4e9.png)

Crack the password using crackstation and found credentials for admin enter into website and it prompted for downoadinf file and so i did 

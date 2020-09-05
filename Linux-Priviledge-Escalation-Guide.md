Linux Priviledge Escalation guide:

https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/

1- Weak file permissions:  (Shadow files read)
         
![Linux_shadow_read](https://user-images.githubusercontent.com/55708909/92296680-d222aa80-ef54-11ea-8dae-da39cd3ef1ca.png)

![Linux_shadow_read_1](https://user-images.githubusercontent.com/55708909/92296755-5ffe9580-ef55-11ea-8c91-fe9b21f62f27.png)

2- Weak file permission:  (Shadow files write)

![Linux_shadow_read_2](https://user-images.githubusercontent.com/55708909/92296828-5de90680-ef56-11ea-9333-c5a1ccd82d52.png)

3- Weak file permission: (Password file read)

![Linux_passwd_read_1](https://user-images.githubusercontent.com/55708909/92296868-eb2c5b00-ef56-11ea-820f-7e33a5d899a1.png)

4- Weak file permission : (Password file write)

![Linux_passwd_read_1](https://user-images.githubusercontent.com/55708909/92296906-5f66fe80-ef57-11ea-81a3-77cac750341f.png)

![LInux_passwd_read_2](https://user-images.githubusercontent.com/55708909/92296908-61c95880-ef57-11ea-93b1-a2db80ad655a.png)

5- Shell escape sequence:

![Linux_shell_escape_1](https://user-images.githubusercontent.com/55708909/92297044-adc8cd00-ef58-11ea-9aa3-ce058605e641.png)

6- Sudo Environment variables:

![Linux_Env_var_1](https://user-images.githubusercontent.com/55708909/92298891-29cc1080-ef6b-11ea-8d87-ad89a8c7ba52.png)

![Linux_Env_var_2](https://user-images.githubusercontent.com/55708909/92298893-2c2e6a80-ef6b-11ea-947f-703f7e8dd797.png)


7- Cronjob (File Permission):

![Linux_Priv_cron_1](https://user-images.githubusercontent.com/55708909/92299071-deb2fd00-ef6c-11ea-8ef0-44c9264cab41.png)

8- Cronjob environment variable:

![Linux_cron_env](https://user-images.githubusercontent.com/55708909/92300464-8e419c80-ef78-11ea-8e9a-8b6b9de73f90.png)

9- Cronjob Wilcharacter:

![LInux_cronjob_wildcharacter](https://user-images.githubusercontent.com/55708909/92300683-6c491980-ef7a-11ea-86cd-a0a358ebab2a.png)

10 SUID/SGID EXECUTE - KNOWN EXPLOITS

find / -type f -a \( -perm -u+s -o -perm -g+s \) -exec ls -l {} \; 2> /dev/null

![Linux_suid_version_exploit](https://user-images.githubusercontent.com/55708909/92300888-44f34c00-ef7c-11ea-8e99-3d59a2d5ac34.png)

11 SUID/SGID OBJECT INJECTION:

![Linux_suid_object_injection_1](https://user-images.githubusercontent.com/55708909/92301086-255d2300-ef7e-11ea-8f85-fe197990797e.png)


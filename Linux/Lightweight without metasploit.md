Lightweight without metasploit

![Lightweight](https://user-images.githubusercontent.com/55708909/91635098-2f79a180-ea13-11ea-83de-eb3504d8b372.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Lightweight -p- 10.10.10.119

![Lightweight_nmap](https://user-images.githubusercontent.com/55708909/91652657-feeb4380-eab6-11ea-9a20-0d0b262dd8e4.png)

I am gonna start with port 80 and let's see what information i can find.

Port 80 user.php page says that you can ssh into box as using your ip as your password i.e.

ssh 10.10.X.X@10.10.10.119

Password: 10.10.X.X

I search for something random and built some methodology and then apply getcap command on various binaries which led to TCPDUMP and then i captured the packet transfer it to my system and then after analysis of various packet led me to ldapuser2 password

![LIghtweight_cap](https://user-images.githubusercontent.com/55708909/91653218-34466000-eabc-11ea-8268-c392f299ccc9.png)

![Lightweight_ldap2](https://user-images.githubusercontent.com/55708909/91653226-44f6d600-eabc-11ea-9b73-d24697319908.png)

After that i find backup.7z file these are steps which i performed.
7za e backup.7z
asking for password 
base64 backup.7z as we can't transfer
save it as backup.7z.enc 
base64 -d backup.7z.enc > backup.7z
7z e backup.7z
again asking for password then i brute force it using this tool https://github.com/Seyptoo/7z-BruteForce.git
password : delete

These are the files which you will see

![Lightweight_files](https://user-images.githubusercontent.com/55708909/91653431-74a6dd80-eabe-11ea-8480-92ccb8836881.png)

Look into each files in status.php you will get ldapuser1 credentials

Something like this :

$password = 'f3ca9d298a553da117442deeb6fa932d';
if ($bind=ldap_bind($ds, $dn, $password)) {

![Lightweight_root](https://user-images.githubusercontent.com/55708909/91653503-2f36e000-eabf-11ea-81f9-e4ce3a98c01b.png)





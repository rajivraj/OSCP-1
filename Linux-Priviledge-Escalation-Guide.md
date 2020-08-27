Linux Priviledge Escalation guide:

https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/

1-Looking at distro version
 
 cat /etc/issue
 
 cat /etc/*-release
 
 cat /etc/lsb-release
 
 cat /etc/redhat-release
 
2- Looking at kernel version 

 cat /proc/version
 
 uname -a
 
 uname -mrs
 
 rpm -q kernel
 
 dmesg |grep Linux

 ls /boot |grep vmlinuz

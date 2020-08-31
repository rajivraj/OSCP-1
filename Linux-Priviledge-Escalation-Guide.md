Linux Priviledge Escalation guide:

https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/

1- Looking at distribution version for possible exploits

cat /etc/issue
cat /etc/*-release
cat /etc/lsb-release
cat /etc/redhat-release

2- Looking at kernel version

cat /proc/version
uname -a
uname -mrx
rpm -q kernel
dmesg |grep linux
ls /boot |grep vmlinuz

3- Looking at environment variables

cat /etc/profile
cat /etc/bashrc
cat ~/.bash_profile
cat ~/.bashrc
cat ~/.bash_logout
set
env

4- Looking at various services
 ps -aux |grep root
 ps -ef  |grep root
 top
 cat /etc/services
 
5- Looking at various applications

 ls -lah /usr/bin
 ls -lah /usr/sbin
 dpkg -l
 rpm -qa
 ls -lah /var/cache/yum
 ls -lah /var/cache/apt/archives0
 
6- Looking at cronjob
 
 cat /etc/crontab
 crontab -l
 

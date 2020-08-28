Grandpa without metasploit

![Grandpa](https://user-images.githubusercontent.com/55708909/91579891-e9b4ce80-e969-11ea-97c4-8dfe8b5579f9.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Grandpa -p- 10.10.10.14

Since it is BOF i Will solve it using metasploit cause i tried so many times the other way but it was not stable.

Fire up my metasploit and search for exploit 2017-7269

Then fill up the requirement and run it you will get shell but not the desired one 

![Grandpa_part_1](https://user-images.githubusercontent.com/55708909/91580907-66947800-e96b-11ea-83ca-b8d06249b8b9.png)

Its better to migrate to other process to get the desirable shell.

![Grandpa_part_2](https://user-images.githubusercontent.com/55708909/91581388-02be7f00-e96c-11ea-958a-2f3b78d5b6a3.png)

After that i use windows-exploit-suggester and as per its recommendation i fire one of them 

![Grandpa_part_3](https://user-images.githubusercontent.com/55708909/91581627-4c0ece80-e96c-11ea-8f4b-635b3c3dab6e.png)



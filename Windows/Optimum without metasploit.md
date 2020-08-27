Optimum without Metasploit:

![Optimum](https://user-images.githubusercontent.com/55708909/91416282-cce6a100-e86c-11ea-84df-635d1770a37d.png)

Starting with Nmap Scan :

Nmap -sC -sV -T4 -A -O -oA Optimum -p- 10.10.10.8

![Optimum_nmap](https://user-images.githubusercontent.com/55708909/91418130-5c8d4f00-e86f-11ea-8155-5beac2946de4.png)

Since we only have one port to enumerate i am gonna start enumerating with my own methodology

![Optimum_web_server](https://user-images.githubusercontent.com/55708909/91420363-3ae19700-e872-11ea-8906-a31de7fb0808.png)

As soon as i saw HttpFileServer httpd 2.3 i google the python version of exploit and found it .

searchsploit 39161.py

![Optimum_edb](https://user-images.githubusercontent.com/55708909/91420998-03bfb580-e873-11ea-9d70-beb63d9d1e66.png)

![Optimum_39161](https://user-images.githubusercontent.com/55708909/91421787-fbb44580-e873-11ea-86fa-deafcf23af24.png)

As per the exploit we need to run a netcat (windows version) and the run the exploit and then only we will get reverse connection from netcat 

in short the exploit first upload a netcat on windows machine and then with the help of netcat we get reverse connection

![Optimum_shell](https://user-images.githubusercontent.com/55708909/91423449-2b644d00-e876-11ea-92aa-b7c4520eb905.png)


We ran windows-exploit-suggester.py and find possible exploit MS16-098

Flags:

![Optimum_flags](https://user-images.githubusercontent.com/55708909/91424701-c578c500-e877-11ea-9973-13572c901c35.png)















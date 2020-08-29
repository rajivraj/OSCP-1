Lacasadepapel without metasploit

![Lacasa](https://user-images.githubusercontent.com/55708909/91628482-c3c91180-e9dd-11ea-84fe-8b50974c2241.png)

Starting with nmap scan:

Nmap -sC -sV -T4 -A -O -oA Lacasa -p- 10.10.10.131

![Lacasa_nmap](https://user-images.githubusercontent.com/55708909/91628523-2d492000-e9de-11ea-9655-a39daca4d6df.png)

As always i will start with port 80.

![Lacasa_port_80](https://user-images.githubusercontent.com/55708909/91628586-c5470980-e9de-11ea-88fa-0440396a0801.png)

Did the usual directory brute force, source-code and other stuff but didn't find anything useful so i will move to port 443

![Lacasa_port_443](https://user-images.githubusercontent.com/55708909/91628624-2e2e8180-e9df-11ea-8feb-542878e9a6c7.png)

It's asking for client certificate so let's generate one.

For that we need key also let's see from which service we can get.

For the key i exploited ftp service and get PSY SHELL

From there i got the ca.key. Now we have the ca.key and ca.crt it's gonna be messy so i shall start

![Lacasa_ca_key](https://user-images.githubusercontent.com/55708909/91628869-81093880-e9e1-11ea-85cf-9177f3816c68.png)

![Lacasa_ca_key1](https://user-images.githubusercontent.com/55708909/91628868-7e0e4800-e9e1-11ea-98db-2d7cc57a59fd.png)

Certificates dealing:
first verify that both certificates are same
1-openssl pkey -in ca.key -pubout
2-openssl  x509 -in ca.crt -pubkey -noout
Create client key:
openssl genrsa -out client.key 4096
Create certificate sign request:
openssl req -new -key client.key -out client.csr 
Signing the certificate:
1-openssl x509 -req -in client.csr -CA ca.crt -CAkey ca.key -set_serial 9001 -extensions client -days 9002 -outform PEM -out client.cer 
2-openssl pkcs12 -export -inkey client.key -in client.cer -out client.p12
3-import two things .p12 (your certificate)  and ca.crt files (authorities) 

And then you will be fine and have access to the website

![Lacasa_access](https://user-images.githubusercontent.com/55708909/91629315-8cf6f980-e9e5-11ea-8861-371aef7c0b37.png)

Tried LFI and was able to see file name user.txt and i thought to get it but fail .Let's try harder

![Lacasa_season1](https://user-images.githubusercontent.com/55708909/91629773-70f55700-e9e9-11ea-9495-d55dbc589238.png)

![Lacasa_access1](https://user-images.githubusercontent.com/55708909/91629779-7a7ebf00-e9e9-11ea-9786-fb12f3e0d82d.png)

Fire up your burp and intercept the request.

When i downloaded the file and opened it. It was  empty huh.

Then i saw a random string in burp.

![Lacasa_download](https://user-images.githubusercontent.com/55708909/91629908-959dfe80-e9ea-11ea-8b64-4efce932a3b1.png)

Decode the highlighted string and you will see that it is name of file and so i though to encode ../user.txt and send the request and maybe i will be able to download the file.

Here i go i have the user.txt file time to get a shell on box.

![Lacasa_user_txt](https://user-images.githubusercontent.com/55708909/91629973-3db3c780-e9eb-11ea-8cf3-bed6e19b3f01.png)

In the same way i got the ssh key but i need a user name so let's see from season 2 if we can get  one or nor

![Lacasa_id_rsa](https://user-images.githubusercontent.com/55708909/91630168-d565e580-e9ec-11ea-9870-0b5c2edf5f7b.png)

From season 2 i tried every name but professor name was lucky and got into the machine.

![Lacasa_root](https://user-images.githubusercontent.com/55708909/91630345-317d3980-e9ee-11ea-83d7-2d727d7f23cc.png)
















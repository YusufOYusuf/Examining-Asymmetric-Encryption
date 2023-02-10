<h1>Examining Asymmetric Encryption</h1>


<h2>Description</h2>
In this lab, I examined asymmetric encryption. Asymmetric encryption, also known as public-key cryptography, was first demonstrated in the 1970s and since then has become a vital part of public security. Like symmetric encryption, it starts with a single large random number, but it uses specialized mathematical equations to turn it into two separate, but tightly interrelated, keys.
<br />



<h2>Environments Used </h2>

- <b>Kali GNU/Linux rolling</b> 

<h2>Utilities and Language </h2>

- <b>Terminal</b>

<h2>Program walk-through:</h2>

<p align="center">
From the left sidebar open up the terminal  <br/>
<img src="https://i.postimg.cc/59RVBvz3/Screen-Shot-2023-02-09-at-11-05-32-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
  
<br />
Next we will generate a RSA key pair. We need to create private key then derive its public key  <br/>
Execute the following command "openssl genrsa -out rsa-key.pem 2048"to generate a random private RSA key and save it as a PEM (private enhanced mail) file <br>
<img src="https://i.postimg.cc/XNhBqsVc/Screen-Shot-2023-02-09-at-11-15-50-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />



<br />
Execute the following command "openssl rsa -in rsa-key.pem -pubout -out rsa-public.pem" to create a public key based on the private key<br>
<img src="https://i.postimg.cc/mrvMqVtS/Screen-Shot-2023-02-09-at-11-20-09-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br>
To view the key files execute command "cat rsa-key.pem" to encode the binary key <br>
PEM files econde the bianry key as Base64 ASCII data. The key itself is labeled as an RSA private key <br>
execute command "cat rsa-public.pem" to mark public key(public keys are shorter and can be exchanged freely<br>
<img src="https://i.postimg.cc/YCYz7hW7/Screen-Shot-2023-02-09-at-11-28-52-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
Generate an eliptic curve key pair (an alternative to RSA) <br>
Enter the "openssl ecparam -list_curves " command to view available curves <br>
Enter the "openssl ecparam -name prime256v1 -genkey -noout -out ecc-key.pem" command to choose a curve and make a private key for it <br>
Now execute the "openssl ec -in ecc-key.pem -pubout -out ecc-public.pem" a public key from the private key <br>
Finally execute the "cat ecc-public.pem" followed by the "cat ecc-key.pem" to display the private and public keys<br>
EC are shorter than RSA keys BUT much stronger do to their algorithms <br>
<img src="https://i.postimg.cc/fymtcVXC/Screen-Shot-2023-02-09-at-11-42-06-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />

















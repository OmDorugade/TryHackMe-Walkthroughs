# <div align="center">[Thompson](https://tryhackme.com/room/bsidesgtthompson)</div>
<div align="center">boot2root machine for FIT and bsides guatemala CTF.
</div>

<div align="center">
  <img width="200" height="150" alt="image" src="https://github.com/user-attachments/assets/69fb6190-470b-42d8-8920-1c6c1cabe581" />
</div>

## 1. user.txt
Using `nmap` we scanned the machine :
<p align="center">
  <img width="940" height="430" alt="image" src="https://github.com/user-attachments/assets/2c952681-6831-4506-9d86-0cffe024476e" />
</p>

Putting ip on web browser we found Apache Tomcat :
<p align="center">
  <img width="940" height="687" alt="image" src="https://github.com/user-attachments/assets/4ae78807-328b-4449-976f-c9a392645142" />
</p>

We click the `Manager App button`. It asks for a username and password. When we click cancel, the website gives an error :
<p align="center">
  <img width="940" height="397" alt="image" src="https://github.com/user-attachments/assets/060e2ff5-2c66-4553-87f4-93e2d3f53e01" />
</p>

We got username and password sign in using that :
<p align="center">
  <img width="689" height="473" alt="image" src="https://github.com/user-attachments/assets/e6a89954-1a47-4a97-9515-62aac6c6f405" />
</p>

Logged in and found that we have upload functionality :
<p align="center">
  <img width="940" height="485" alt="image" src="https://github.com/user-attachments/assets/815cb8f0-02d0-4738-8a4c-5a03b422a723" />
</p>

We uploaded reverse.phtml which has reverse shell code but we can only upload .war file :
<p align="center">
  <img width="940" height="126" alt="image" src="https://github.com/user-attachments/assets/2393fed6-e1e7-421a-a4d0-38e0de3b3819" />
</p>

Searching online about reverse shell in war file we found we can create with `msfvenom` :
<p align="center">
  <img width="940" height="658" alt="image" src="https://github.com/user-attachments/assets/916d85a7-abb1-412f-93f3-39bf67e8147c" />
</p>

We created payload on our machine :
<p align="center">
  <img width="940" height="93" alt="image" src="https://github.com/user-attachments/assets/95bbd896-f58e-45d4-a4da-39cbe42854ea" />
</p>

Upload created shell.war on the target website :
<p align="center">
  <img width="940" height="387" alt="image" src="https://github.com/user-attachments/assets/619b8611-973f-42be-8e25-b6186c99c516" />
</p>

We can view our file on manager page under Application section :
<p align="center">
  <img width="940" height="369" alt="image" src="https://github.com/user-attachments/assets/3da9e5d9-6835-43ca-937a-9ed61a1388b3" />
</p>

Set up a netcat listener and click on the shell file we uploaded to get reverse shell on our machine :
<p align="center">
  <img width="927" height="572" alt="image" src="https://github.com/user-attachments/assets/90851019-f982-471f-b95d-9021110d715a" />
</p>
 
We did 

  

















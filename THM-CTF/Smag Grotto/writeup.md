# <div align="center">[Smag Grotto CTF](https://tryhackme.com/room/smaggrotto)</div>
<div align="center">Follow the yellow brick road.
</div>

<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/5f1407fa-0dec-4eea-94ac-2939d7aab375" />
</div>

## 1. What is the user flag?
Enumerate the machine using `nmap` and `gobuster` :
<p align="center">
  <img width="787" height="706" alt="image" src="https://github.com/user-attachments/assets/97e5a152-11ac-4887-a1e1-3c58b2384382" />
</p>

We found a page `/mail` checked it and got a wireshark file :
<p align="center">
  <img width="1011" height="636" alt="image" src="https://github.com/user-attachments/assets/9a584b6b-93bb-4a18-8b8c-6582c194e5ca" />
</p>

Download the wireshark file using `wget` :
<p align="center">
  <img width="940" height="409" alt="image" src="https://github.com/user-attachments/assets/ac370cd7-06ce-4615-9126-a9b298665ad3" />
</p>

Open it using wireshark and go through the packets found an HTTP POST login request in which we found a new domain and some credentials in that wireshark file :
<p align="center">
  <img width="940" height="612" alt="image" src="https://github.com/user-attachments/assets/9ee3f3bc-a01b-47f1-8192-4b5838df9951" />
</p>

Add development.smag.thm to `/etc/hosts` file :
<p align="center">
  <img width="708" height="415" alt="image" src="https://github.com/user-attachments/assets/17146f7a-ae9b-4880-93c0-9fc4a73b74fd" />
</p>

Logged in and found we can execute some commands so now we can get a reverse shell :
<p align="center">
  <img width="901" height="542" alt="image" src="https://github.com/user-attachments/assets/a3460cc6-7b55-42d9-b1c1-0da7baae89da" />
</p>

We Set up a listener on our machine and got access but we were not able to read user.txt :
<p align="center">
  <img width="940" height="868" alt="image" src="https://github.com/user-attachments/assets/c50801eb-ec77-486b-bec3-549fc5878e7a" />
</p>

After this we did `cat /etc/passwd` and we found `jake` has some permission greater than `www-data` :
<p align="center">
  <img width="726" height="497" alt="image" src="https://github.com/user-attachments/assets/809125e7-db1f-449a-8007-1a68189026da" />
</p>

And also used `cat /etc/crontab` to look what was running and found that we can read and write this file :
<p align="center">
  <img width="871" height="307" alt="image" src="https://github.com/user-attachments/assets/84a67092-8590-4599-8b01-5015684998e1" />
</p>

We created ssh private and public key we used `ssh keygen` :
<p align="center">
  <img width="940" height="860" alt="image" src="https://github.com/user-attachments/assets/2c4a32be-d316-4670-bade-c599ec292972" />
</p>

Copy public key and paste in that `/opt/.backup/jake_id_rsa.pub.backup` file :
<p align="center">
  <img width="940" height="313" alt="image" src="https://github.com/user-attachments/assets/39402f73-4cff-4125-8912-20af1badf2cc" />
</p>

Then use private key for login from our local machine and got access :
<p align="center">
  <img width="940" height="505" alt="image" src="https://github.com/user-attachments/assets/af4c3f94-c88b-4534-a43f-8ef4c84bb661" />
</p>

Did `sudo -l` to gain root access :
<p align="center">
  <img width="940" height="127" alt="image" src="https://github.com/user-attachments/assets/9ecbb9c8-b66f-48e5-a80d-5181956021fd" />
</p>

Found this github repo to gain root access :
<p align="center">
  <img width="940" height="869" alt="image" src="https://github.com/user-attachments/assets/cd3ff299-c13f-4c5d-aad4-3658b69d47f8" />
</p>

Finally got





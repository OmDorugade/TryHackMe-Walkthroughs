# <div align="center">[Creative CTF](https://tryhackme.com/room/creative)</div>
<div align="center">Exploit a vulnerable web application and some misconfigurations to gain root privileges.
</div>

<div align="center">
  <img width="200" height="200" alt="bab044b44df50036b61681f0778fced2" src="https://github.com/user-attachments/assets/f1941699-5a87-43e5-b805-3bedc7185048" />
</div>

## 1. What is user.txt?
To get access to website creative.thm we need to add this to our `/etc/host` folder :
<p align="center">
  <img width="945" height="512" alt="image" src="https://github.com/user-attachments/assets/d7eecb4b-c57b-44de-ab9e-70760058e447" />
</p>

Performed port scanning using `nmap` :
<p align="center">
  <img width="552" height="231" alt="image" src="https://github.com/user-attachments/assets/6a19858b-f686-4b79-8203-f751e48f201e" />
</p>

Could not find anything interesting using `gobuster` :
<p align="center">
  <img width="990" height="411" alt="image" src="https://github.com/user-attachments/assets/4b9e1ff5-3e02-4814-b382-7d21de6b3157" />
</p>

So used subdomain enumeration using `wfuzz` and found a subdomain :
<p align="center">
  <img width="1192" height="445" alt="image" src="https://github.com/user-attachments/assets/f0174b9f-526f-4233-8c5f-27e03e638c94" />
</p>

This subdomain was for testing urls to see if the url is alive or not :
<p align="center">
  <img width="997" height="282" alt="image" src="https://github.com/user-attachments/assets/788475fc-fa50-4080-af74-7c06a98279d4" />
</p>

We checked the machine url i.e `creative.thm` :
<p align="center">
  <img width="940" height="736" alt="image" src="https://github.com/user-attachments/assets/29ba4603-0947-45db-9cb2-920051583229" />
</p>

Did some research and tried to take our own access and check for any open port :
<p align="center">
  <img width="752" height="417" alt="image" src="https://github.com/user-attachments/assets/d93b38e7-2125-4a6a-9b25-9b14d7f6e47b" />
</p>

Found the port and did this :
<p align="center">
  <img width="1187" height="440" alt="image" src="https://github.com/user-attachments/assets/82c51638-35c8-44f9-8290-d8e55d71ee05" />
</p>

And got directory list :
<p align="center">
  <img width="930" height="762" alt="image" src="https://github.com/user-attachments/assets/41533947-85de-49c9-b4d8-cc4eb79bf738" />
</p>

Went to the home folder and found `user.txt` :
<p align="center">
  <img width="837" height="537" alt="image" src="https://github.com/user-attachments/assets/a9235649-8346-4f4f-b993-33dd6f376629" />
</p>

Then using the url test got our flag :
<p align="center">
  <img width="1161" height="392" alt="image" src="https://github.com/user-attachments/assets/1a40cad7-241f-4e56-8541-3ad63e18ddc3" />
</p>

<p align="center">
  <img width="1053" height="230" alt="image" src="https://github.com/user-attachments/assets/74282640-e06f-4449-8550-37194cde7c7b" />
</p>

```
9a1ce90a7653d74ab98630b47b8b4a84
```

## 2. What is root.txt?
Enumerate different folders and found `ssh` keys  :
<p align="center">
  <img width="935" height="327" alt="image" src="https://github.com/user-attachments/assets/8f7c98f3-081b-43c5-8feb-43980d96e273" />
</p>











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








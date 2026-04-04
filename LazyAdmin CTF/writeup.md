# <div align="center">[LazyAdmin](https://tryhackme.com/room/lazyadmin)</div>
<div align="center">Easy linux machine to practice your skills</div>
<br>
<div align="center">
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/f6ac0f26-e067-4963-b4b2-07c07791ce53"/>
</div>

## 1. What is the user flag?
Enumerate the machine using `gobuster` and `nmap` we found this:
<p align="center">
   <img width="847" height="216" alt="image" src="https://github.com/user-attachments/assets/3027bf27-fa8a-4d40-902d-a30616e2fc48" />
</p>

Looking at the website we found it is using `SweetRice` as website management system.
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/ab6d8b8e-a1a8-4118-9f4e-5a99435e5cb7" />
</p>

Searched in `exploit.db` and found this:
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/716374cf-86ca-41c3-b399-6df956b0f46a" />
</p>

After this again run `gobuster` on `http://ip/content/` and found this :
<p align="center">
   <img width="776" height="241" alt="image" src="https://github.com/user-attachments/assets/e51009dd-ca8f-448e-9be4-0a1d9b80183b" />
</p>

In that directory found a `mysql_backup/` directory and in that found backup:
<p align="center">
   <img width="578" height="317" alt="image" src="https://github.com/user-attachments/assets/83810b74-ef88-48fa-a99e-6f7ad0d65984" />
</p>






















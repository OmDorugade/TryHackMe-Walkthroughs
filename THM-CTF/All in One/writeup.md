# <div align="center">[All in One](https://tryhackme.com/room/allinonemj)</div>
<div align="center">This is a fun box where you will get to exploit the system in several ways. Few intended and unintended paths to getting user and root access.
</div>

<div align="center">
  <img width="300" height="250" alt="image" src="https://github.com/user-attachments/assets/b27259bc-8863-43e0-a040-4255f212bfa7" />
</div>

## 1. user.txt
Enumerate the machine using `nmap` :
<p align="center">
  <img width="940" height="672" alt="image" src="https://github.com/user-attachments/assets/9cee1d0b-c92a-4d9c-8729-b32492b0a806" />
</p>

Looking at the `nmap` result `ftp` is on and we can login as anonymous :
<p align="center">
  <img width="866" height="821" alt="image" src="https://github.com/user-attachments/assets/7d1f7f7f-7714-432a-b345-1e9b81c7e060" />
</p>

Nothing found on `ftp` , Now used `gobuster` for directory brute forcing :
<p align="center">
  <img width="940" height="717" alt="image" src="https://github.com/user-attachments/assets/19042c86-1df0-40a8-a920-7f168ebe0a92" />
</p>

Cheking the `/hackathons` page :
<p align="center">
  <img width="940" height="275" alt="image" src="https://github.com/user-attachments/assets/7aa9f605-776b-4af3-88a3-6d7665a25108" />
</p>










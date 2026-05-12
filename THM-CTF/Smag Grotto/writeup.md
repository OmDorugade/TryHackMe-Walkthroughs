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

Open it using wireshark and go through the packets found an HTTP POST login request :
<p align="center">
  <img width="940" height="612" alt="image" src="https://github.com/user-attachments/assets/9ee3f3bc-a01b-47f1-8192-4b5838df9951" />
</p>

We found a new domain and some credentials in that wireshark file 













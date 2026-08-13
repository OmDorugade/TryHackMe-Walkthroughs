# <div align="center">[Dreaming](https://tryhackme.com/room/dreaming)</div>
<div align="center">Solve the riddle that dreams have woven.
</div>

<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/aa2b46e7-6a9c-4fc8-9ddd-a9b66456aaaa" />
</div>

## 1. What is the Lucien Flag?
Using `nmap` we scan the machine for open ports and service detection with `nmap` default scripts :
<p align="center">
  <img width="940" height="381" alt="image" src="https://github.com/user-attachments/assets/bb2043f9-12f6-4ce0-a085-4524e88e2fa1" />
</p>

Found Apache2 Default Page Running :
<p align="center">
  <img width="940" height="601" alt="image" src="https://github.com/user-attachments/assets/804a4092-2214-4457-9167-be35f7bfd4e7" />
</p>

Using `gobuster` we did directory brute force and found a path :
<p align="center">
  <img width="940" height="524" alt="image" src="https://github.com/user-attachments/assets/c3c3b3be-084b-4382-bc68-1cbd458fbb77" />
</p>

Visit the path and we found a folder named pluck:
<p align="center">
  <img width="940" height="449" alt="image" src="https://github.com/user-attachments/assets/7764a5b7-3f5b-48cc-b15f-a728905cc2ed" />
</p>

Opening the folder we got a webpage :
<p align="center">
  <img width="940" height="318" alt="image" src="https://github.com/user-attachments/assets/fb6673f5-c900-4f82-9310-466ed9aed3fc" />
</p>

Click on admin












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

Click on admin word we will get a login page which will ask for a password :
<p align="center">
  <img width="940" height="400" alt="image" src="https://github.com/user-attachments/assets/d9a57bec-dea8-4bbc-a2c7-00e968ba8f3c" />
</p>

Trying Common passwords we found the password is `password` :
<p align="center">
  <img width="940" height="626" alt="image" src="https://github.com/user-attachments/assets/fb70d1e8-9631-4b37-b1b9-f0bdaaaa614d" />
</p>

We found it using `pluck` as CMS and the version is `4.7.13` which is vulnerable we found this on `ExploitDB` :
<p align="center">
  <img width="940" height="228" alt="image" src="https://github.com/user-attachments/assets/7256dddf-ce82-4efe-b4d1-80fd3ba2bce0" />
</p>

Download the exploit and look if we have to make any changes :
<p align="center">
  <img width="940" height="744" alt="image" src="https://github.com/user-attachments/assets/1b3a6f80-5d68-40cd-ac24-9d4bb26d377d" />
</p>

Upload it on target machine :
<p align="center">
  <img width="940" height="158" alt="image" src="https://github.com/user-attachments/assets/cd2e1728-59e8-42f3-9875-1fa88328821b" />
</p>

We have uploaded `p0wnyshell` script on target machine and to get better terminal used `revshells.com` command :
<p align="center">
  <img width="940" height="649" alt="image" src="https://github.com/user-attachments/assets/c8d7dc9e-4c65-4e53-9d33-4d55810b05ec" />
</p>

Started `netcat` listner on our machine and got reverse shell :
<p align="center">
  <img width="938" height="766" alt="image" src="https://github.com/user-attachments/assets/92745c6b-8c54-4e44-8f99-50b851fd2ea8" />
</p>

There were two scripts in python in `opt` folder :
<p align="center">
  <img width="940" height="276" alt="image" src="https://github.com/user-attachments/assets/26ca32ae-2ca5-4b60-bb18-516dc09f1d47" />
</p>

We read the `test.py` file













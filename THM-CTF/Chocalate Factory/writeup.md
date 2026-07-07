# <div align="center">[Chocalate Factory](https://tryhackme.com/room/chocolatefactory)</div>
<div align="center">A Charlie And The Chocolate Factory themed room, revisit Willy Wonka's chocolate factory!
</div>

<div align="center">
  <img width="200" height="250" alt="image" src="https://github.com/user-attachments/assets/7eb8d82c-b4c5-48ea-9ecd-1d21b1095804" />
</div>

## 1. Enter the key you found!
Visit the machine ip we found a login page :
<p align="center">
  <img width="940" height="533" alt="image" src="https://github.com/user-attachments/assets/71a9f71b-7c33-49ba-919d-1365716ea967" />
</p>

Using `nmap` scan for open ports :
<p align="center">
  <img width="940" height="837" alt="image" src="https://github.com/user-attachments/assets/76d6731e-b4ee-4862-a0b7-d2057d57daf3" />
</p>

<p align="center">
  <img width="940" height="464" alt="image" src="https://github.com/user-attachments/assets/c0eb2b05-73fa-4244-814e-bcd87abddd36" />
</p>

Now we know `ftp` service is running so we use it for our advantage :
<p align="center">
  <img width="1707" height="497" alt="image" src="https://github.com/user-attachments/assets/3e2343ae-c140-4d3f-9ab0-a3eecf0836a7" />
</p>

We found a `jpg` file and extracted it using `steghide` to get hidden files :
<p align="center">
  <img width="463" height="145" alt="image" src="https://github.com/user-attachments/assets/38d15e1c-9dab-4715-90cb-1ef0b2534813" />
</p>

We read the `b64` txt file :
<p align="center">
  <img width="940" height="754" alt="image" src="https://github.com/user-attachments/assets/0b93405b-d941-45d3-aecc-18c6294c0d57" />
</p>

Decode the data using `base64decode.org` and found a username `charlie` and its password hash :
<p align="center">
  <img width="940" height="671" alt="image" src="https://github.com/user-attachments/assets/721d01a8-68b4-4a96-a8b0-1f618e346757" />
</p>

Using `hashes.com` identify the hash :
<p align="center">
  <img width="940" height="305" alt="image" src="https://github.com/user-attachments/assets/442c2edb-5b7c-4b87-8530-fede95d25594" />
</p>

Now we 














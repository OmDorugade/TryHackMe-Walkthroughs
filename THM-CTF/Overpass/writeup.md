# <div align="center">[Overpass](https://tryhackme.com/room/overpass)</div>
<div align="center">What happens when some broke CompSci students make a password manager?</div>

<div align="center">
   <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/abcb5567-7caa-44df-ac3d-de4b2bb3c1fe" />
</div>

## 1. Hack the machine and get the flag in user.txt
Enumerate the machine using `namp` :
<p align="center">
   <img width="940" height="505" alt="image" src="https://github.com/user-attachments/assets/31183791-d434-45a2-8e7b-090dc7993ca2" />
</p>

Using `gobuster` we did directory brute force and found some pages :
<p align="center">
   <img width="940" height="421" alt="image" src="https://github.com/user-attachments/assets/2897095c-24f6-426b-b1ee-0e58eebf9221" />
</p>

Checking the `/aboutus` page :
<p align="center">
   <img width="940" height="340" alt="image" src="https://github.com/user-attachments/assets/857880aa-26f1-48ad-9dd0-583195dcb162" />
</p>

It took some time and research we have to set session cookie and myCookie value , we got this by reading the `login.js` script :
<p align="center">
   <img width="396" height="71" alt="image" src="https://github.com/user-attachments/assets/f3b0e9df-1ad0-4166-9db0-d24f4e219bf8" />
</p>

After entering above refresh `/admin` page and we got a RSA key :
<p align="center">
   <img width="940" height="975" alt="image" src="https://github.com/user-attachments/assets/e71f485e-56cd-4620-b3e3-804412c0b375" />
</p>










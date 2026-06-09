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

We will use the above RSA key using `ssh2john` :
<p align="center">
   <img width="542" height="109" alt="image" src="https://github.com/user-attachments/assets/2437b2d3-f2f6-447c-a29b-9d73e7e3842d" />
</p>

Using `john` we crack the password and change some permissions :
<p align="center">
   <img width="940" height="295" alt="image" src="https://github.com/user-attachments/assets/6e1c47a7-da71-4eca-8d12-a0589d90da91" />
</p>

Using the password we logged in as james using `ssh` and found user.txt :
<p align="center">
   <img width="940" height="818" alt="image" src="https://github.com/user-attachments/assets/fc5793ea-d0d1-4969-b50b-30215041b217" />
</p>

```
thm{65c1aaf000506e56996822c6281e6bf7}
```

## 2. Escalate your privileges and get the flag in root.txt
Now to get root access we checked crontab for any running scripts :
<p align="center"> 
   <img width="940" height="385" alt="image" src="https://github.com/user-attachments/assets/c83a8401-a1ec-4796-97aa-118d78a20acf" />
</p>

We made script and added reverse shell code :
<p align="center">
   <img width="828" height="206" alt="image" src="https://github.com/user-attachments/assets/725062b5-1071-4bcf-998b-2ec87ef5bf70" />
</p>

Uploaded it on target machine :
<p align="center">
   <img width="940" height="581" alt="image" src="https://github.com/user-attachments/assets/fd53bfe1-9c08-4799-8fb1-e1e26478dad9" />






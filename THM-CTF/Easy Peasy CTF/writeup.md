# <div align="center">[Easy Peasy CTF](https://tryhackme.com/room/easypeasyctf)</div>
<div align="center">Practice using tools such as Nmap and GoBuster to locate a hidden directory to get initial access to a vulnerable machine. Then escalate your privileges through a vulnerable cronjob.
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/4346d12f-372e-42c6-9130-c617c8b8a43c" />
</div>

## 1. How many ports are open?
<p align="center">
  <img width="940" height="1017" alt="image" src="https://github.com/user-attachments/assets/bdd02275-8229-4818-b40e-2214e20c84c2" />
</p>

```
3
```

## 2. What is the version of nginx?
```
1.16.1
```

## 3. What is running on the highest port?
```
Apache
```

## 4. Using GoBuster, find flag 1.
Used `feroxbuster` :
<p align="center">
  <img width="1215" height="685" alt="image" src="https://github.com/user-attachments/assets/d8727dae-a027-4a40-a39e-6744d9b6faab" />
</p>

Found a directory and a base64 hash :
<p align="center">
  <img width="772" height="398" alt="image" src="https://github.com/user-attachments/assets/b7d8d5a6-e18c-4f1f-8ad7-f0355ffd183c" />
</p>

Decoded it and got our first flag :
<p align="center">
  <img width="402" height="642" alt="image" src="https://github.com/user-attachments/assets/e1212b4d-917b-404c-a14f-f185de2af700" />
</p>

```
flag{f1rs7_fl4g}
```

## 5. Further enumerate the machine, what is flag 2?
We have `robots.txt` file on `65524` port we checked that and got 
<p align="center">
  <img width="657" height="183" alt="image" src="https://github.com/user-attachments/assets/2255f94a-373a-4f3f-bfb4-15f0cae990a9" />
</p>

That is a MD5 hash after decoding it :
<p align="center">
  <img width="940" height="225" alt="image" src="https://github.com/user-attachments/assets/8f96f27e-7abb-4a30-a5cf-43cca0d4aeb6" />
</p>

```
flag{1m_s3c0nd_fl4g}
```

## 6.Crack the hash with easypeasy.txt, What is the flag 3?
Checking the source code of the page we found :
<p align="center">
  <img width="940" height="866" alt="image" src="https://github.com/user-attachments/assets/def934da-3a68-429b-b3e2-5c0d23f56f00" />
</p>

We Got a base62 hash we decode it and we got a new directory :
<p align="center">
  <img width="1147" height="766" alt="image" src="https://github.com/user-attachments/assets/8424a0b2-36c3-4f9e-8083-c468a46ab4c6" />
</p>

Visit the page and checked the source code we got another hash and a jpg file to download :
<p align="center">
  <img width="925" height="391" alt="image" src="https://github.com/user-attachments/assets/54f76b34-854d-41f2-bee0-7b95cf368b8c" />
</p>

Crack the hash and found this :
<p align="center">
  <img width="940" height="256" alt="image" src="https://github.com/user-attachments/assets/ba676a13-a954-4280-ba95-69cea6687c67" />
</p>

Found the Third flag :
<p align="center">
  <img width="1185" height="723" alt="image" src="https://github.com/user-attachments/assets/f665fc85-7970-4b4f-a056-13f094179292" />
</p>

```
flag{9fdafbd64c47471a8f54cd3fc64cd312}
```

## 7. What is the hidden directory?
```
/n0th1ng3ls3m4tt3r
```

## 8. what is the password?
```
mypasswordforthatjob
```

## 9. What is the password to login to the machine via SSH?
We have the jpg started looking online for tools and found how to use them :
<p align="center">
  <img width="833" height="207" alt="image" src="https://github.com/user-attachments/assets/be217c82-12f8-4a9d-b082-6709417b7530" />
</p>

<p align="center">
  <img width="1165" height="710" alt="image" src="https://github.com/user-attachments/assets/4a1ebbd2-93a7-4cbc-8783-3d39f9098376" />
</p>

Used CyberChef to crack the binary code and found the password:
<p align="center">
  <img width="1020" height="390" alt="image" src="https://github.com/user-attachments/assets/e5e7533b-d2a0-4b4c-8dd1-ad0703c60593" />
</p>

```
iconvertedmypasswordtobinary
```

## 10. User.txt

We know the username used to log in ssh and found the flag is rotated :
<p align="center">
  <img width="940" height="569" alt="image" src="https://github.com/user-attachments/assets/2f6215a4-1420-4477-8489-5b070c0f0039" />
</p>

First searched online about this and found this is `ROT13` used it to decode it :
<p align="center">
  <img width="782" height="425" alt="image" src="https://github.com/user-attachments/assets/1d0f86b8-cb4c-4b08-b174-1a6d000ba988" />
</p>

```
flag{n0wits33msn0rm4l}
```

## 11. Root.txt
Checked the `crontab` and found a script running :
<p align="center">
  <img width="940" height="1037" alt="image" src="https://github.com/user-attachments/assets/4c03e6dc-0346-402a-bf84-b84d53dfc8f7" />
</p>

We were able to edit the file and set up a reverse shell code :
<p align="center">
  <img width="613" height="963" alt="image" src="https://github.com/user-attachments/assets/ca6a09e6-0088-43a2-98d7-70e7e5b0d947" />
</p>

Got the reverse shell and finally got our root.txt :
<p align="center">
  <img width="940" height="1035" alt="image" src="https://github.com/user-attachments/assets/da9c1247-08a6-4cbd-8092-5774f50c2cf7" />
</p>

```
flag{63a9f0ea7bb98050796b649e85481845}
```











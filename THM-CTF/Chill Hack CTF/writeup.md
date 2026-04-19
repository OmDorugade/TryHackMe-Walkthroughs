# <div align="center">[Chill Hack CTF](https://tryhackme.com/room/chillhack)</div>
<div align="center">This is a machine that allows you to practise web app hacking and privilege escalation.
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/b1cf8eac-dca0-4a4a-ade3-24a26119cb42" />
</div>

## 1. User Flag
Enumerate the machine using `nmap` for port scanning and with `gobuster` for finding more web pages.
<p align="center">
  <img width="1465" height="677" alt="image" src="https://github.com/user-attachments/assets/b04752cd-0a73-4124-accf-ab2e3f8f70d2" />
</p>

<p align="center">
  <img width="710" height="487" alt="image" src="https://github.com/user-attachments/assets/851fcf1b-8ec7-47d8-b01b-ed6067cadccf" />
</p>

Using the information from `nmap` scan we logged in using `ftp` as `Anonymous` and just press enter for `password`:
<p align="center">
  <img width="846" height="328" alt="image" src="https://github.com/user-attachments/assets/b595b3ac-8727-4d0f-a6b8-ec81a0f0575b" />
</p>

Found this note :
<p align="center">
  <img width="1020" height="97" alt="image" src="https://github.com/user-attachments/assets/996123a5-ca5b-4949-bd31-2412c0cb4c9f" />
</p>

Using the `gobuter`  we found a page `/secret` we went there and we saw we can execute some commands and got reverse shell:
<p align="center">
  <img width="1007" height="536" alt="image" src="https://github.com/user-attachments/assets/6ee90ab8-cbef-4b0d-9d24-45193df653f0" />
</p>

We were logged in as `www-data` which does not have permissions :
<p align="center">
  <img width="940" height="818" alt="image" src="https://github.com/user-attachments/assets/057928b6-13c8-4498-a1b6-ee16979b4d32" />
</p>

We used the python command for better terminal and also found the `./.helpline.sh` file and got our first flag :
<p align="center">
  <img width="742" height="482" alt="image" src="https://github.com/user-attachments/assets/74275fbf-340b-4c82-9514-67e1f82225bd" />
</p>

```
{USER-FLAG: e8vpd3323cfvlp0qpxxx9qtr5iq37oww}
```

## 2.Root Flag
It took some time but found some credentials in `index.php` file of root for `mysql` : 
<p align="center">
  <img width="940" height="827" alt="image" src="https://github.com/user-attachments/assets/3e691e06-693e-4c50-8889-c04bea5a4a23" />
</p>

Used this credentials and logged in `mysql` and found this :
<p align="center">
  <img width="940" height="953" alt="image" src="https://github.com/user-attachments/assets/2b72cef6-ea05-43a3-89de-2c7e45866979" />
</p>

There was another file called `hacker.jpg` so download this on our machine using python :
<p align="center">
  <img width="940" height="1046" alt="image" src="https://github.com/user-attachments/assets/f08bd97a-44e5-4b3c-a47e-578a563a802c" />
</p>

Then used `crackstation.net` to crack the hashes :
<p align="center">
  <img width="1185" height="617" alt="image" src="https://github.com/user-attachments/assets/7ce0d5e7-12cf-4230-a7ab-d79973c27578" />
</p>

Using `wget` we got the `hacker.jpg` file and used different tools like `steghide` , `zip2john` and `john` to get something from image , we found a `backup.zip` :
<p align="center">
  <img width="940" height="793" alt="image" src="https://github.com/user-attachments/assets/5ac27788-6716-4e2f-96ca-a503c32cab69" />
</p>

Found base64 enoded password in the file :
<p align="center">
  <img width="940" height="872" alt="image" src="https://github.com/user-attachments/assets/18b78143-8a6d-479b-ac2c-cfef4003c030" />
</p>

Using `base64dfecode` we decoded the hash :
<p align="center">
  <img width="555" height="565" alt="image" src="https://github.com/user-attachments/assets/aba2d958-5188-4d06-8b9f-9f75216ea5d3" />
</p>









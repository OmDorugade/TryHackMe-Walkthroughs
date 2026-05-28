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

Cheking the `/hackathons` page but found nothing usefull :
<p align="center">
  <img width="940" height="275" alt="image" src="https://github.com/user-attachments/assets/7aa9f605-776b-4af3-88a3-6d7665a25108" />
</p>

Then we visited the machine ip and we get to know it is a wordpress website so we can do wordpress scan :
<p align="center">
  <img width="801" height="600" alt="image" src="https://github.com/user-attachments/assets/6318b0ad-b5b9-4de3-949a-6737988d1a75" />
</p>

<p align="center">
  <img width="940" height="603" alt="image" src="https://github.com/user-attachments/assets/f9967682-5b4b-42ab-b690-f6aaf21030a1" />
</p>

We found an exploit on exploit.db :
<p align="center">
  <img width="940" height="838" alt="image" src="https://github.com/user-attachments/assets/cdd729f2-13cc-4861-bfbd-652821eca80e" />
</p>

Read the exploit carefully and found we can do `/etc/passwd` with the full link :
<p align="center">
  <img width="940" height="201" alt="image" src="https://github.com/user-attachments/assets/bc7e26e4-b4ea-4117-a2aa-673859b5cd27" />
</p>

Found this `php://filter/convert.base64-encode/resource=../../../../../wp-config.php` :
<p align="center">
  <img width="940" height="142" alt="image" src="https://github.com/user-attachments/assets/2b9fda8f-5fba-43e2-b200-dc8804412e1b" />
</p>

Copy and Paste the `base64` code on CyberChef :
<p align="center">
  <img width="940" height="448" alt="image" src="https://github.com/user-attachments/assets/554300e1-8ca2-420a-a2db-d2868d784756" />
</p>

We found a username and password in the output and logged in using credentials :
<p align="center">
  <img width="877" height="980" alt="image" src="https://github.com/user-attachments/assets/1e9c8b17-45ee-4a42-998b-5a3a5740f973" />
</p>

We can upload our reverse shell code on Appearance page :
<p align="center">
  <img width="940" height="492" alt="image" src="https://github.com/user-attachments/assets/4504ee0a-450f-4fa0-ae4e-55eafd21c476" />
</p>

After uploading access it to get a reverse shell access :
<p align="center">
  <img width="940" height="137" alt="image" src="https://github.com/user-attachments/assets/93400555-2ca5-497e-b8fd-49f9a47c587f" />
</p>

Got access but was not able to read userflag :
<p align="center">
  <img width="940" height="827" alt="image" src="https://github.com/user-attachments/assets/0de8e326-c09a-4143-a223-1962e5315536" />
</p>

Checking the home files again we found `hint.txt` and it revealed some usefull information 



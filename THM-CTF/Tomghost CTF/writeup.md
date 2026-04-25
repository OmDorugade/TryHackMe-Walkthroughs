# <div align="center">[Tomghost](https://tryhackme.com/room/tomghost)</div>
<div align="center">Identify recent vulnerabilities to try exploit the system or read files that you should not have access to.
</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/55d7f57a-3973-4122-bc02-e37046111dda" />
</div>

## 1. Compromise this machine and obtain user.txt
Using `nmap` we performed port scanning :
<p align="center">
  <img width="567" height="332" alt="image" src="https://github.com/user-attachments/assets/a392fc72-18bf-4a9f-89bf-5f181c0b24e4" />
</p>

Looked online for `tomcat_ghostcat` and found we can use metasploit to exploit the it :
<p align="center">
  <img width="940" height="819" alt="image" src="https://github.com/user-attachments/assets/2dc9b971-13d0-4125-8cf9-e81bee7a46fd" />
</p>

Got some credentials from the exploit we ran used them and logged in using ssh :
<p align="center">
  <img width="940" height="652" alt="image" src="https://github.com/user-attachments/assets/89492d47-dda8-41df-a4e7-b3919fbd2068" />
</p>

Got our first flag :
<p align="center">
  <img width="527" height="370" alt="image" src="https://github.com/user-attachments/assets/013ce85a-c3b1-4c3a-971e-c784c0e2b824" />
</p>

```
THM{GhostCat_1s_so_cr4sy}
```

## 2. Escalate privileges and obtain root.txt
Than did `sudo -l ` but we cannot use it , there was another file :
<p align="center">
  <img width="687" height="211" alt="image" src="https://github.com/user-attachments/assets/51931a36-a94e-41af-9e86-14077eee1af1" />
</p>

We checked the file and we have pgp key :
<p align="center">
  <img width="940" height="729" alt="image" src="https://github.com/user-attachments/assets/1fcd4976-942a-4af3-af0f-5e76e1d2ba0c" />
</p>

Using `gpg2john` and `john` we cracked the hash :
<p align="center">
  <img width="940" height="857" alt="image" src="https://github.com/user-attachments/assets/4b66574a-ac40-4bd2-b063-b7246da5a838" />
</p>
 
Again logged in using the credentials and did `sudo -l` :
<p align="center">
  <img width="940" height="921" alt="image" src="https://github.com/user-attachments/assets/b9edc207-b514-457b-a2db-ef68c5a4722e" />
</p>

We searched online about the `sudo -l` output and found this command :
<p align="center">
  <img width="940" height="436" alt="image" src="https://github.com/user-attachments/assets/4a37927a-120d-4900-8314-b3f7b955b7a2" />
</p>

We got the root :
<p align="center">
  <img width="892" height="309" alt="image" src="https://github.com/user-attachments/assets/bc2e8b05-d60f-495d-9279-43a1fe4d847f" />
</p>









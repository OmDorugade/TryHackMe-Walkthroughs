# <div align="center">[Valley CTF](https://tryhackme.com/room/valleype)</div>
<div align="center">Can you find your way into the Valley?
</div>

<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/273ea781-3992-4540-a88d-fb7e58438097" />
</div>

## 1. What is the user flag?
Enumerate the machine using `nmap` and `gobuster` :
<p align="center">
  <img width="1067" height="557" alt="image" src="https://github.com/user-attachments/assets/d843a2fb-04d6-45fb-9cf5-4be8c8717787" />
</p>

Found a page and enumerated further and found another page :
<p align="center">
  <img width="1087" height="661" alt="image" src="https://github.com/user-attachments/assets/85977e7a-8ad3-4c2a-ba47-035697bd98f7" />
</p>

Now enumerated the new page :
<p align="center">
  <img width="1107" height="737" alt="image" src="https://github.com/user-attachments/assets/1ca4d014-e323-4fb4-a9ad-429ff7830199" />
</p>

Checking the source code found a txt page :
<p align="center">
  <img width="940" height="912" alt="image" src="https://github.com/user-attachments/assets/44f77ab8-b769-4286-a7f7-542300a4e43a" />
</p>

Checking the txt page found this :
<p align="center">
  <img width="802" height="156" alt="image" src="https://github.com/user-attachments/assets/42eb2600-2868-4c60-a6dc-cb81c482b898" />
</p>

Scanning all ports with `nmap` and found this :
<p align="center">
  <img width="861" height="431" alt="image" src="https://github.com/user-attachments/assets/8c9371d8-8e3d-4811-8d8e-6716736c3e50" />
</p>

With the help of the notes on the txt page we used ftp login and found some wireshark files :
<p align="center">
  <img width="1122" height="633" alt="image" src="https://github.com/user-attachments/assets/2a7740ed-dfe2-4ec7-9995-72caaa613f7b" />
</p>

Checking the three wireshark file we found some credentials :
<p align="center">
  <img width="940" height="597" alt="image" src="https://github.com/user-attachments/assets/e2b8ef54-6b67-475b-805f-fa6b6e873281" />
</p>

Found the user flag :
<p align="center">
  <img width="677" height="535" alt="image" src="https://github.com/user-attachments/assets/c4550aa8-14af-4146-8b43-e705223ed027" />
</p>

```
THM{k@l1_1n_th3_v@lley}
```

## 2. What is the root flag?
We were not able to do `sudo -l` :
<p align="center">
  <img width="630" height="307" alt="image" src="https://github.com/user-attachments/assets/dfb4026d-2fd3-463f-98d9-68249b12ab11" />
</p>

Found some files using scp took them on our machine :
<p align="center">
  <img width="940" height="155" alt="image" src="https://github.com/user-attachments/assets/9f643cc6-2bf2-4a2e-b5aa-6bcf40597f50" />
</p>

Reading the files we found an MD5 hash :
<p align="center">
  <img width="1101" height="540" alt="image" src="https://github.com/user-attachments/assets/ba19b333-e672-4cad-9d99-f086380e2f90" />
</p>

<p align="center">
  <img width="638" height="735" alt="image" src="https://github.com/user-attachments/assets/09ccb536-fb33-42fb-9b7a-2aa648cfddd8" />
</p>




# <div align="center">[Source CTF](https://tryhackme.com/room/source)</div>
<div align="center">Exploit a recent vulnerability and hack Webmin, a web-based system configuration tool.
</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/e71991d2-a4c6-4b7f-b1ba-0f065ea33373" />
</div>

## 1. user.txt
Enumerating the machine using `nmap` for port scanning :
<p align="center">
  <img width="1155" height="432" alt="image" src="https://github.com/user-attachments/assets/f1aa4741-5d45-4816-95c9-fd99de03b7e3" />
</p>

Looked at source code but found nothing :
<p align="center">
  <img width="1338" height="615" alt="image" src="https://github.com/user-attachments/assets/450ef895-a681-440b-9efb-93b00588efc4" />
</p>

We were also not able to directory brute force using `gobuster` :
<p align="center">
  <img width="940" height="613" alt="image" src="https://github.com/user-attachments/assets/dd1ad157-7839-4fa1-b73b-7722a1d52206" />
</p>

Website is using webmin so search in `metasploit` :
<p align="center">
  <img width="940" height="858" alt="image" src="https://github.com/user-attachments/assets/97108a3e-3d3f-4beb-bdde-f21b697745c9" />
</p>

Using the 10th payload and setting the options :
<p align="center">
  <img width="940" height="817" alt="image" src="https://github.com/user-attachments/assets/35fd16ea-0a6d-4f34-8b68-396b708d862e" />
</p>

Using `exploit` command we got the access of the machine :
<p align="center">
  <img width="940" height="863" alt="image" src="https://github.com/user-attachments/assets/67b344dc-a4a5-4a5a-b055-11f799daa329" />
</p>

For interactive terminal used python library pty : 

  






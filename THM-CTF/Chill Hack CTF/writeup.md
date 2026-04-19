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

  <img width="940" height="818" alt="image" src="https://github.com/user-attachments/assets/057928b6-13c8-4498-a1b6-ee16979b4d32" />

















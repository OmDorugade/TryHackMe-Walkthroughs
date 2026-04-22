# <div align="center">[Jack-of-all-trades CTF](https://tryhackme.com/room/jackofalltrades)</div>
<div align="center">Boot-to-root originally designed for Securi-Tay 2020
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/2c59d81d-15cb-4183-b857-631ec20f564f" />
</div>

## 1. User Flag
Enumerate the machine using `nmap` for port scanning :
<p align="center">
  <img width="1083" height="562" alt="image" src="https://github.com/user-attachments/assets/4c400d90-3576-48e8-865d-b86320b545da" />
</p>

Nmap scan shows http running on port `22` so we have to configure our browser settings so we can access it  : 
<p align="center">
  <img width="940" height="904" alt="image" src="https://github.com/user-attachments/assets/657f11eb-9363-4582-9f69-58340ffc91ae" />
</p>

Further we used `feroxbuster` to scan the website for hidden directories :

  <img width="1191" height="470" alt="image" src="https://github.com/user-attachments/assets/7ba0598f-c22e-483e-a3fb-8cc8de5a0e2f" />













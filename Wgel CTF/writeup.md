# <div align="center">[Wgel CTF](https://tryhackme.com/room/wgelctf)</div>
<div align="center">Can you exfiltrate the root flag?</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/cd7d2590-9942-4adc-adf0-4bedf12c695e" />
</div>

## 1. User flag
Performed `nmap` for port-scanning and `gobuster` to find hidden diretories :
<p align="center">
  <img width="827" height="660" alt="image" src="https://github.com/user-attachments/assets/94bb1419-312d-4a65-87b8-8636c9a6747f" />
</p>

Then visit the `source code` of the website and found this :
<p align="center">
  <img width="965" height="611" alt="image" src="https://github.com/user-attachments/assets/f5745900-0928-4f1e-85ca-926a0f5f1e55" />
</p>

Lets visit the `sitemap` and further enumerated this page :
<p align="center">
  <img width="1242" height="583" alt="image" src="https://github.com/user-attachments/assets/10b8156e-e792-406d-a46b-9b2662a8fa65" />
</p>

We know that in `.ssh` folder we may found someones `RSA Private Key` :
<p align="center">
  <img width="626" height="781" alt="image" src="https://github.com/user-attachments/assets/938299c1-328e-4b0e-ad45-eeb48d59b390" />
</p>

Copy paste the `id_rsa` and give permissions and log in using `ssh` :
<p align="center">
  <img width="868" height="620" alt="image" src="https://github.com/user-attachments/assets/5ff66b2b-df88-4926-ac36-a7c92c901673" />
</p>










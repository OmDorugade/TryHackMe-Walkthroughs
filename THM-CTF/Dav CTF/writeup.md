# <div align="center">[Dav CTF](https://tryhackme.com/room/bsidesgtdav)</div>
<div align="center">boot2root machine for FIT and bsides guatemala CTF
</div>
<br>
<div align="center">
  <img width="260" height="260" alt="image" src="https://github.com/user-attachments/assets/818280ea-4302-4787-92c4-de3be929b795" />
</div>

## 1. user.txt
Enumerate the machine using `nmap` and use `gobuster` for diretory brute force :
<p align="center">
  <img width="1361" height="735" alt="image" src="https://github.com/user-attachments/assets/55caba5c-d5c1-4ecd-89f4-dc76fca94155" />
</p>

When we goto the `/webdav` it ask us for username and password , search online about this and found a github repo :
<p align="center">
  <img width="940" height="963" alt="image" src="https://github.com/user-attachments/assets/f54824ba-012e-470a-b64d-b5ac4fba6975" />
</p>

Found a file named `/passwd.dav` open it and found this :
<p align="center">
  <img width="940" height="379" alt="image" src="https://github.com/user-attachments/assets/904b6a40-1bf5-40df-a3f6-3b8177f29573" />
</p>

Searched tool to upload file on `webdav` found a tool name `cadaver` :
<p align="center">
  <img width="940" height="788" alt="image" src="https://github.com/user-attachments/assets/0599f79c-7fbe-4f8c-a855-3e1254c31a81" />
</p>

Not able to crack the hash but we are able to upload php code :
<p align="center">
  <img width="1357" height="448" alt="image" src="https://github.com/user-attachments/assets/99c924f9-484a-4b2f-a5f6-9be10aedbe16" />
</p>

We set up a listener on our machine and clicked on the `reverse.phtml` file and got reverse shell and found user.txt :
<p align="center">
  <img width="492" height="68" alt="image" src="https://github.com/user-attachments/assets/fdbdea3c-d905-455b-91de-c33e41b2e3fa" />
</p>









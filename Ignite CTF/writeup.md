# <div align="center">[Ignite CTF](https://tryhackme.com/room/ignite)</div>
<div align="center">A new start-up has a few issues with their web server.
</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/5f5cfd7a-d257-4117-9c04-a87810084e44" />
</div>

## 1. User.txt
Start the machine and perform `nmap` for port scanning and `gobuster` for finding directories :
<p align="center">
  <img width="695" height="702" alt="image" src="https://github.com/user-attachments/assets/c29e8ac4-8a7b-4fdb-ad0b-839ba3a3b9f4" />
</p>

After looking at the webiste we found that it is using `Fuel CMS` we goto `exploit.db` and found this :
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/bbbc53da-c2bc-4731-b70c-8d54aed2290b" />
</p>

Download the python script and execute it and we found that we can enter some commands:
<p align="center">
  <img width="595" height="308" alt="image" src="https://github.com/user-attachments/assets/e2a1b6dc-bb54-4e33-a7ec-530d9fd25c10" />
</p>

So did online search for this and got this online :
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/d5601e0e-fd99-4057-8e91-a2cfdb355056" />
</p>

We used the reverse shell payload and set up listener on our local machine and:










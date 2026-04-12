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

We used the reverse shell payload and set up listener on our local machine and got our first flag:
<p align="center">
  <img width="1465" height="492" alt="image" src="https://github.com/user-attachments/assets/1afc80ab-5dbd-4ce2-b9e8-d6fb2ef364cc" />
</p>

```
6470e394cbf6dab6a91682cc8585059b
```

## 2.Root.txt
There were some steps on the website on the default page we looked at it and started to find `database.php` file :
<p align="center">
  <img width="1322" height="710" alt="image" src="https://github.com/user-attachments/assets/d5924bf1-38f5-46d3-99a3-aa508f266705" />
</p>

Read the file using `cat` and found the credentials of `root` :
<p align="center">
  <img width="602" height="591" alt="image" src="https://github.com/user-attachments/assets/3b8c972d-dae2-44f3-b7cf-2525e37a7643" />
</p>

Using `python` we made an interactive terminal and using the credentials of `root` we found our final flag :
<p align="center">
  <img width="532" height="303" alt="image" src="https://github.com/user-attachments/assets/e1682bb2-0c69-4b77-8706-a039c3c9aa14" />
</p>

b9bbcb33e11b80be759c4e844862482d





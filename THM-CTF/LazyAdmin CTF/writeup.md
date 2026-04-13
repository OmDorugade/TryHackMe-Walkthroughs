# <div align="center">[LazyAdmin](https://tryhackme.com/room/lazyadmin)</div>
<div align="center">Easy linux machine to practice your skills</div>
<br>
<div align="center">
   <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/f6ac0f26-e067-4963-b4b2-07c07791ce53"/>
</div>

## 1. What is the user flag?
Enumerate the machine using `gobuster` and `nmap` we found this:
<p align="center">
   <img width="847" height="216" alt="image" src="https://github.com/user-attachments/assets/3027bf27-fa8a-4d40-902d-a30616e2fc48" />
</p>

Looking at the website we found it is using `SweetRice` as website management system.
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/ab6d8b8e-a1a8-4118-9f4e-5a99435e5cb7" />
</p>

Searched in `exploit.db` and found this:
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/716374cf-86ca-41c3-b399-6df956b0f46a" />
</p>

After this again run `gobuster` on `http://ip/content/` and found this :
<p align="center">
   <img width="776" height="241" alt="image" src="https://github.com/user-attachments/assets/e51009dd-ca8f-448e-9be4-0a1d9b80183b" />
</p>

In that directory found a `mysql_backup/` directory and in that found backup:
<p align="center">
   <img width="578" height="317" alt="image" src="https://github.com/user-attachments/assets/83810b74-ef88-48fa-a99e-6f7ad0d65984" />
</p>

We used `cat mysql_backup.sql` file and found this:
<p align="center">
   <img width="832" height="232" alt="image" src="https://github.com/user-attachments/assets/e6a90afd-5bdd-437d-975c-a74f1bf20ca7" />
</p>

Used `crackstation.net` to crack the hash and logged in as manager :
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/6711de2c-ed26-4435-9ba3-67aa9688a963" />
</p>

Looked at different pages and found this page where we can upload a file , we uploaded `reverse shell` file to gain access:
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/305db8e8-6497-4d01-9e56-074ab2f910c2" />
</p>

Set up a listener on our machine and clicked on the uploaded file, and got our first `user.txt` flag :
<p align="center">
   <img width="940" height="407" alt="image" src="https://github.com/user-attachments/assets/dbf074de-024b-4511-a4b4-598263260496" />
</p>

```
THM{63e5bce9271952aad1113b6f1ac28a07}
```

## 2. What is the root flag?
For privilege escalation we used `sudo -l` and found this file:
<p align="center">
   <img width="940" height="133" alt="image" src="https://github.com/user-attachments/assets/2ee5aff9-7215-476f-aa46-c51fe46bba66" />
</p>

We used `cat` to look what insisde the file and found another `copy.sh` file :
<p align="center">
   <img width="940" height="134" alt="image" src="https://github.com/user-attachments/assets/a5f65e30-438d-4043-8808-8fc5a41ab7dc" />
</p>

We read the file and uploaded another reverse shell to get `root`:
<p align="center">
   <img width="940" height="76" alt="image" src="https://github.com/user-attachments/assets/460f29fe-d088-4785-bcdd-2cb542601297" />
</p>

Then set up a listener on our machine and run `sudo /usr/bin/perl /home/itguy/backup.pl` and got our `root.txt` flag :
<p align="center">
   <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/013a7c4e-6dd6-431b-a696-925332cfec2a" />
</p>

```
THM{6637f41d0177b6f37cb20d775124699f}
```

Room Completed !






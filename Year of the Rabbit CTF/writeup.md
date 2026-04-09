# <div align="center">[Year of the Rabbit CTF](https://tryhackme.com/room/yearoftherabbit)</div>
<div align="center">Time to enter the warren...</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/45af5007-f1d4-41eb-9d38-c0775f4cfad7" />
</div>

## 1. What is the user flag?
Use `gobuster` to find directories : 
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/fea68f06-88aa-47be-b455-a02b8d0c0138" />
</p>

Check the `style.css` file :
<p align="center">
  <img width="695" height="755" alt="image" src="https://github.com/user-attachments/assets/8c42a039-243d-4c9f-86b9-28a82c8da6d4" />
</p>

Lets take look at the `/sup3r_s3cret_fl4g/` :
<p align="center">
  <img width="940" height="875" alt="image" src="https://github.com/user-attachments/assets/9d8b05bb-903f-4aeb-ba88-9e6eb4e84c22" />
</p>

Searched online about this and followed this steps :

1.I am using `firefox` browser we need to type `about:config` 

2.Search about `javascript.enabled`

3.Make it `false`
<p align="center">
  <img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/893ddf31-7713-4e90-91f4-413fff572f44" />
</p>

4.Reload the page and use `Burpsuite` to capture the response for a new directory called `/WExYY2Cv-qU/` :
<p align="center">
  <img width="940" height="600" alt="image" src="https://github.com/user-attachments/assets/07451231-576f-4688-ac93-8c9d88287700" />
</p>

Visit the directory we got a new file , Just use `cat` and the file name :
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/b9e6c5bc-829a-4a5e-a019-92e218810745" />
</p>

Then we used `hydra` to get `ftp` login credentials :
<p align="center">
  <img width="940" height="216" alt="image" src="https://github.com/user-attachments/assets/69385f48-fc35-4180-b320-cd33c3dd2b36" />
</p>

We logged in `ftp` and found a file `eli's_Creds.txt` , look into the file using `cat` :
<p align="center">
  <img width="940" height="709" alt="image" src="https://github.com/user-attachments/assets/fc0b6bc2-01e5-4093-a45f-925a246f4744" />
</p>

<p align="center">
  <img width="940" height="196" alt="image" src="https://github.com/user-attachments/assets/796787d8-d83e-4580-98b9-d32a2889c652" />
</p>

Then we used Chatgpt for identifying what is in that file :
<p align="center">
  <img width="940" height="531" alt="image" src="https://github.com/user-attachments/assets/61d09550-8689-42d7-9dd2-32b1b4261141" />
</p>

To decode it we used `dcode.fr` and we found `eli's password` :
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/1f1c3ce0-c886-4ced-8f18-1ec67433ee79" />
</p>

Use `ssh` for login and found this message :
<p align="center">
  <img width="817" height="263" alt="image" src="https://github.com/user-attachments/assets/88018df2-5e32-4280-865e-1993b55d0d0e" />
</p>

We used `locate` for finding the s3cr3t and found the file used `cat` and got `gwendoline` password :
<p align="center">
  <img width="682" height="147" alt="image" src="https://github.com/user-attachments/assets/6b02c39d-6443-431b-a3d3-7ea93bf4978f" />
</p>

Used `su gwendoline` and enter the password and find the user.txt :
<p align="center">
  <img width="700" height="133" alt="image" src="https://github.com/user-attachments/assets/004873d9-7959-4b84-8854-5eadb3e0ae30" />
</p>

```
THM{1107174691af9ff3681d2b5bdb5740b1589bae53}
```

## 2. What is the root flag?
We did `sudo -V` and found this :
<p align="center">
  <img width="478" height="99" alt="image" src="https://github.com/user-attachments/assets/6f7f6ef5-dbc5-4522-ba31-6f969cca0f9b" />
</p>

Searched online about this and found this in `exploit.db` :
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/7701e10b-9873-4c4c-97a4-5ff0541c5789" />
</p>








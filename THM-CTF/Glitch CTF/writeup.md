# <div align="center">[Glitch CTF](https://tryhackme.com/room/glitch)</div>
<div align="center">Challenge showcasing a web app and simple privilege escalation. Can you find the glitch?
</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/ef4c0262-5ae4-425d-891a-0a86c40a64ce" />
</div>

## 1.What is your access token?
Enumerate the machine using `nmap` for port scanning :
<p align="center">
  <img width="822" height="632" alt="image" src="https://github.com/user-attachments/assets/ca51f328-8da3-485b-80df-04fad3b5f57c" />
</p>

Using `gobuster` we did directory brute forcing and found a page :
<p align="center">
 <img width="962" height="633" alt="image" src="https://github.com/user-attachments/assets/474d68a8-7920-47b8-8529-f23aa9a344a8" />
</p>

We took a look at the source code and found that we can access `/api` page :
<p align="center">
  <img width="943" height="765" alt="image" src="https://github.com/user-attachments/assets/60b7f1a9-1058-4e91-b604-d3a8ca5963a6" />
</p>

We looked at the page and got a token in base64 encoded :
<p align="center">
  <img width="800" height="509" alt="image" src="https://github.com/user-attachments/assets/32f0b957-a794-40a4-8593-16920a11ffa1" />
</p>

Using base64 we decoded it :
<p align="center">
  <img width="910" height="733" alt="image" src="https://github.com/user-attachments/assets/e47b3e64-b762-4fb9-bcd9-bd6413f51b68" />
</p>

```
this_is_not_real
```

## 2. What is the content of user.txt?
Enumerated further on `/api` page using `gobuster` and also try to check that can we use any parameter :
<p align="center">
  <img width="922" height="733" alt="image" src="https://github.com/user-attachments/assets/cffc97f5-541b-41b7-a9ed-7bbe55c31c8d" />
</p>

Checking the `/api/items` and using `cmd` parameter :
<p align="center">
  <img width="940" height="936" alt="image" src="https://github.com/user-attachments/assets/781eda75-d13e-4810-872d-a0a15948ace1" />
</p>

Using revshells.com we try to make a payload for reverse shell :
<p align="center">
  <img width="940" height="146" alt="image" src="https://github.com/user-attachments/assets/cdd1a802-3c14-4418-a9be-8a5221d97bd9" />
</p>

Set up a listener on our machine and using `curl` we POST our payload and found our user.txt flag :
<p align="center">
  <img width="940" height="608" alt="image" src="https://github.com/user-attachments/assets/d1dd3008-d795-445a-983e-e9bb830a9b6a" />
</p>

```
THM{i_don't_know_why}
```

## 3.What is the content of root.txt?
We were not able to do `sudo -l` and looking at some directories we found `.firefox` directory :
<p align="center">
  <img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/adbbd8a4-6a9e-46a3-b9ea-02fd7c25cb9b" />
</p>

Using tar got that folder in our local machine :
<p align="center">
  <img width="869" height="380" alt="image" src="https://github.com/user-attachments/assets/623ce52f-a87c-4e10-b9a9-a0fb69cce9ee" />
</p>

Found a github directory to decrypt firefox file :
<p align="center">
  <img width="1097" height="887" alt="image" src="https://github.com/user-attachments/assets/6b2b7a61-fff8-4dfc-bfe6-c16f09831578" />
</p>

<p align="center">
  <img width="602" height="130" alt="image" src="https://github.com/user-attachments/assets/474dd369-3f57-4d14-ae2c-42906a0b0ed3" />
</p>

We got the credentials of `v0id` and logged in and got our root.txt :
<p align="center">
  <img width="458" height="606" alt="image" src="https://github.com/user-attachments/assets/bd189f2b-9567-4e10-b194-66de20f9ba49" />
</p>

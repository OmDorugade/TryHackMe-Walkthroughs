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
















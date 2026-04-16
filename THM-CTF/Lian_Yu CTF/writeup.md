# <div align="center">[Lian_Yu CTF](https://tryhackme.com/room/lianyu)</div>
<div align="center">A beginner level security challenge
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/9e846602-8905-4f00-bc02-c42eb1e5bd07" />
</div>

## 1. What is the Web Directory you found?
First did `gobuster` scan found this directory `/island` :

<p align="center">
  <img width="1067" height="523" alt="image" src="https://github.com/user-attachments/assets/506ccba5-7452-4dbc-8c9b-bdcc2803c69d" />
</p>

Further did scan with `gobuster` on `http://ip/island/` and found this :
<p align="center">
  <img width="911" height="412" alt="image" src="https://github.com/user-attachments/assets/216526d5-e80c-43b3-b620-166da5568cff" />
</p>

```
2100
```

## 2. What is the file name you found?
Checked the `source code` and found this :
<p align="center">
  <img width="807" height="462" alt="image" src="https://github.com/user-attachments/assets/27fa6db0-1ae6-4b68-a565-6be7c7e9017e" />
</p>

Then used `FUFF` to enumerate :
<p align="center">
  <img width="940" height="530" alt="image" src="https://github.com/user-attachments/assets/46cf3d39-096d-4542-b872-55e4b02fc7f8" />
</p>

Searched online about the random string and found that it is `BASE58` then used `CYBERCHEF` to decode it :
<p align="center">
  <img width="821" height="391" alt="image" src="https://github.com/user-attachments/assets/6772abf4-793b-4d59-9c3b-280c3d084f91" />
</p>









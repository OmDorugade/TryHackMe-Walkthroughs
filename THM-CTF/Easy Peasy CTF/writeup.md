# <div align="center">[Easy Peasy CTF](https://tryhackme.com/room/easypeasyctf)</div>
<div align="center">Practice using tools such as Nmap and GoBuster to locate a hidden directory to get initial access to a vulnerable machine. Then escalate your privileges through a vulnerable cronjob.
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/4346d12f-372e-42c6-9130-c617c8b8a43c" />
</div>

## 1. How many ports are open?
<p align="center">
  <img width="940" height="1017" alt="image" src="https://github.com/user-attachments/assets/bdd02275-8229-4818-b40e-2214e20c84c2" />
</p>

```
3
```

## 2. What is the version of nginx?
```
1.16.1
```

## 3. What is running on the highest port?
```
Apache
```

## 4. Using GoBuster, find flag 1.
Used `feroxbuster` :
<p align="center">
  <img width="1215" height="685" alt="image" src="https://github.com/user-attachments/assets/d8727dae-a027-4a40-a39e-6744d9b6faab" />
</p>

Found a directory and a base64 hash :
<p align="center">
  <img width="772" height="398" alt="image" src="https://github.com/user-attachments/assets/b7d8d5a6-e18c-4f1f-8ad7-f0355ffd183c" />
</p>

Decoded it and got our first flag :

  <img width="402" height="642" alt="image" src="https://github.com/user-attachments/assets/e1212b4d-917b-404c-a14f-f185de2af700" />










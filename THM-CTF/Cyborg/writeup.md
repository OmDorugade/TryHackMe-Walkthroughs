# <div align="center">[Cyborg](https://tryhackme.com/room/cyborgt8)</div>
<div align="center">A box involving encrypted archives, source code analysis and more.
</div>

<div align="center">
  <img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/b17dfc4f-c2bc-42c0-808a-c0c5a3af7567" />
</div>

## 1.Scan the machine, how many ports are open?
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




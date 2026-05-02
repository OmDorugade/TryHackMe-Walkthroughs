# <div align="center">[UltraTech CTF](https://tryhackme.com/room/ultratech1)</div>
<div align="center">The basics of Penetration Testing, Enumeration, Privilege Escalation and WebApp testing.
</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/32c618e2-6ba4-415f-b02d-b30ec304b743" />
</div>

## 1. Which software is using the port 8081?
<p align="center">
  <img width="940" height="954" alt="image" src="https://github.com/user-attachments/assets/680be2a5-3c51-4fd6-a9ee-dc500bd3cc4c" />
</p>

```
Node.js
```

## 2. Which other non-standard port is used?

```
31331
```

## 3. Which software using this port?

```
Apache
```

## 4. Which GNU/Linux distribution seems to be used?

```
Ubuntu
```

## 5. The software using the port 8081 is a REST api, how many of its routes are used by the web application?

```
2
```

## 6. There is a database lying around, what is its filename?
Used `gobuster` for directory traversal and found `robots.txt` page :
<p align="center">
  <img width="673" height="146" alt="image" src="https://github.com/user-attachments/assets/3c40dd09-15b6-4ee2-a8c0-d492dad2d1b4" />
</>

Visited the page and found more pages : 
<p align="center">
  <img width="717" height="152" alt="image" src="https://github.com/user-attachments/assets/3ac2558d-c305-4c47-b5c1-6cf177d61d68" />
</p>

Found login page :
<p align="center">
  <img width="777" height="688" alt="image" src="https://github.com/user-attachments/assets/e8059a7d-a22a-4f88-9b98-f9e8973bba5d" />
</p>

```
```













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

Performed Enumeration on website by looking at different page source code and found this :
<p align="center">
  <img width="715" height="692" alt="image" src="https://github.com/user-attachments/assets/16a9adc0-a6f5-4e79-bf50-388e80ba94ac" />
</p>

Read above code carefully and understand it we can run cmd using /ping?ip=`ls ` but on port 8081 also only ` ` this symbol can run commands 
<p align="center">
  <img width="573" height="92" alt="image" src="https://github.com/user-attachments/assets/4a8bfdd6-5aa0-4f8f-a907-8f36776419de" />
</p>

```
utech.db.sqlite
```

## 7. What is the first user's password hash?
Look at the file using `cat` :
<p align="center">
  <img width="968" height="153" alt="image" src="https://github.com/user-attachments/assets/ebbe43e8-09a0-4a87-90ef-403e7f3430b0" />
</p>

We found MD5 hash and cracked it :
<p align="center">
  <img width="866" height="457" alt="image" src="https://github.com/user-attachments/assets/d43a918b-2843-46e4-bcab-01b417c49836" />
</p>

```
f357a0c52799563c7c7b76c1e7543a32
```

## 8. What is the password associated with this hash?

```
n100906
```

## 9. What are the first 9 characters of the root user's private SSH key?
Using the information we found till now :
<p align="center">
  <img width="1042" height="557" alt="image" src="https://github.com/user-attachments/assets/bdb1e9e0-0261-4a12-b839-024b90555fb3" />
</p>

Gain access using the credentials and used `gftobins` to gain access :
<p align="center">
  <img width="1022" height="668" alt="image" src="https://github.com/user-attachments/assets/cbaeff4b-5e5d-4ed1-9d2a-353911d7a068" />
</p>

The last task was to find the SSH key :
<p align="center">
  <img width="878" height="1127" alt="image" src="https://github.com/user-attachments/assets/3fbe2959-72b7-4ae7-95f4-6ddf220c4ed2" />
</p>






# <div align="center">[Couch CTF](https://tryhackme.com/room/couch)</div>
<div align="center">Hack into a vulnerable database server that collects and stores data in JSON-based document formats, in this semi-guided challenge.
</div>

<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/c49f4885-579a-4969-8822-b52693e03381" />
</div>

## 1. Scan the machine. How many ports are open?
Using `nmap` we performed port scanning :
<p align="center">
  <img width="1123" height="703" alt="image" src="https://github.com/user-attachments/assets/c3b30e38-9cf3-44be-9106-5a16474fae12" />
</p>

```
2
```

## 2. What is the database management system installed on the server?
Searched online about `COUCHDB` and found this :
<p align="center">
  <img width="1152" height="676" alt="image" src="https://github.com/user-attachments/assets/adba2f6a-fac7-4fc5-a9bb-a4aef6c6f089" />
</p>

```
couchdb
```

## 3. What port is the database management system running on?

```
5984
```

## 4. What is the version of the management system installed on the server?

```
1.6.1
```

## 5. What is the path for the web administration tool for this database management system?
Look at the 2nd question image we have found the ans :
<p align="center">
  <img width="1047" height="345" alt="image" src="https://github.com/user-attachments/assets/db4cf53a-507a-4a9a-9da4-2821e7a5dfa2" />
</p>

```
_utils
```

## 6. What is the path to list all databases in the web browser of the database management system?
Look at the 2nd question image we have found the ans :

```
_all_dbs
```

## 7. What are the credentials found in the web administration tool?
Looking at all files on the database server we found this page :
<p align="center">
  <img width="1122" height="311" alt="image" src="https://github.com/user-attachments/assets/46af9d2e-f893-464d-a7b7-c3dbbf7ba156" />
</p>

```
atena:t4qfzcc4qN##
```

## 8. Compromise the machine and locate user.txt
With the help of credentials we found we used `ssh` for login and found our user flag :
<p align="center">
  <img width="592" height="342" alt="image" src="https://github.com/user-attachments/assets/54084b7b-a0c7-4de0-8fff-3ed06e7d6a77" />
</p>















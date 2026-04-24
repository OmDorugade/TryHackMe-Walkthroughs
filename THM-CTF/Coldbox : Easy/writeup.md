# <div align="center">[ColdBox : Easy](https://tryhackme.com/room/colddboxeasy)</div>
<div align="center">An easy level machine with multiple ways to escalate privileges.
</div>

<div align="center">
  <img width="350" height="250" alt="image" src="https://github.com/user-attachments/assets/72d55493-4ee7-47c9-bae9-bf1fa620526c" />
</div>

## 1. user.txt
Visit the machine ip and we get to know that it is a wordpress site :
<p align="center">
  <img width="763" height="592" alt="image" src="https://github.com/user-attachments/assets/05215ad8-5f0a-4945-bd76-6be82ad90222" />
</p>

Using the tool `wpscan` we enumerated the website also used user and password list to get any credentials :
<p align="center">
  <img width="1240" height="673" alt="image" src="https://github.com/user-attachments/assets/c10f2029-430f-48ef-b1c9-db3762739cab" />
</p>

Found the credentials :
<p align="center">
  <img width="940" height="846" alt="image" src="https://github.com/user-attachments/assets/230a6b80-e0a5-4374-8d4b-76698ead914d" />
</p>

Logging using the credentials and now we visited each page and found this php page where we can upload our reverse php shell code :
<p align="center">
  <img width="981" height="776" alt="image" src="https://github.com/user-attachments/assets/77a82ece-3e45-4598-9160-93339b07faa3" />
</p>

Then we have to access that page using the page url so we can get reverse shell on our machine :
<p align="center">
  <img width="902" height="432" alt="image" src="https://github.com/user-attachments/assets/3676d4d7-20c5-4f71-8da9-3ac6f64aed7f" />
</p>
  
Got the reverse shell on our machine but we cannot read the files beacuse we are `www-data` for now so we need to get a user session :
<p align="center">
  <img width="923" height="702" alt="image" src="https://github.com/user-attachments/assets/23713584-d6d3-4f6d-9e64-ef42f57f8bcf" />
</p>

Enumerating further we found a file `wp-config.php` in `/var/html/www/` which had username `c0ldd` and password :
<p align="center">
  <img width="940" height="899" alt="image" src="https://github.com/user-attachments/assets/70bf686a-b756-42ab-b9e5-4273225927a7" />
</p>

With the credentials logged in using ssh and found our first flag :
<p align="center">
  <img width="940" height="555" alt="image" src="https://github.com/user-attachments/assets/09439e65-0e73-4e3a-bf25-4b1427d76c34" />
</p>

```
RmVsaWNpZGFkZXMsIHByaW1lciBuaXZlbCBjb25zZWd1aWRvIQ==
```







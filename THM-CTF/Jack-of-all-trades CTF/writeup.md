# <div align="center">[Jack-of-all-trades CTF](https://tryhackme.com/room/jackofalltrades)</div>
<div align="center">Boot-to-root originally designed for Securi-Tay 2020
</div>
<br>
<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/2c59d81d-15cb-4183-b857-631ec20f564f" />
</div>

## 1. User Flag
Enumerate the machine using `nmap` for port scanning :
<p align="center">
  <img width="1083" height="562" alt="image" src="https://github.com/user-attachments/assets/4c400d90-3576-48e8-865d-b86320b545da" />
</p>

Nmap scan shows http running on port `22` so we have to configure our browser settings so we can access it  : 
<p align="center">
  <img width="940" height="904" alt="image" src="https://github.com/user-attachments/assets/657f11eb-9363-4582-9f69-58340ffc91ae" />
</p>

Further we used `feroxbuster` to scan the website for hidden directories and some files :
<p align="center">
  <img width="1191" height="470" alt="image" src="https://github.com/user-attachments/assets/7ba0598f-c22e-483e-a3fb-8cc8de5a0e2f" />
</p>

Using `curl` we got some `base64` hash :
<p align="center">
  <img width="797" height="426" alt="image" src="https://github.com/user-attachments/assets/7d49a36c-314f-4fb9-8270-94a9f4de94b3" />
</p>

We decoded it using `base64decode.org` website and got a password :
<p align="center">
  <img width="1166" height="667" alt="image" src="https://github.com/user-attachments/assets/4e8ab8b3-f82f-4412-be54-1e965b374a3d" />
</p>

Lets get back to the files we found on the target machine website and try to decode it using `steghide` :
<p align="center">
  <img width="1016" height="578" alt="image" src="https://github.com/user-attachments/assets/fe3b812a-c6f7-40a1-8b5e-64a06dac8e6d" />
</p>

If we looked at the `curl` image above we also found `/recovery.php` page and we entered the username and password we found :
<p align="center">
  <img width="1037" height="271" alt="image" src="https://github.com/user-attachments/assets/2c139f4a-fde1-4a43-87cb-a0ef6b523e6a" />
</p>

After using the credentials we got this page saying :
<p align="center">
  <img width="907" height="205" alt="image" src="https://github.com/user-attachments/assets/ee10cab4-5293-4988-a40c-d721375f24ff" />
</p>

Just used `?cmd=` after the `index.php` and got this :
<p align="center">
  <img width="967" height="143" alt="image" src="https://github.com/user-attachments/assets/9f1ad1e9-41fe-47bf-be3c-684c01162e51" />
</p>

Now used reverse shell commands to get access :
<p align="center">
  <img width="1110" height="178" alt="image" src="https://github.com/user-attachments/assets/41cb49a1-a6bc-48f9-aab2-1f55c861762a" />
</p>

Got the reverse shell on our machine and found some password list :
<p align="center">
  <img width="562" height="691" alt="image" src="https://github.com/user-attachments/assets/e27ef411-c1d8-4e9b-a47a-aa4ec03f6224" />
</p>

Using `hydra` we got the password for `ssh` and found an `user.jpg` file using `python` we took that file to our machine :
<p align="center">
  <img width="713" height="657" alt="image" src="https://github.com/user-attachments/assets/7660f6e8-97eb-4ef4-88a6-e896eeba2cb7" />
</p>

Finally we got our first flag : 
<p align="center">
  <img width="1012" height="686" alt="image" src="https://github.com/user-attachments/assets/ba99dd74-a462-4cdb-b657-a083f6362e9d" />
</p>

```
securi-tay2020_{p3ngu1n-hunt3r-3xtr40rd1n41r3}
```














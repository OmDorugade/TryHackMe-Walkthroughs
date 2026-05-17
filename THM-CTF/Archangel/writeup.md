# <div align="center">[Archangel](https://tryhackme.com/room/archangel)</div>
<div align="center">Boot2root, Web exploitation, Privilege escalation, LFI.
</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/c84bec53-68bf-4a47-b1ce-0e6c6c3aef6c" />
</div>

## 1. Find a different hostname
On the home page we can see mail of `mafialive.thm` :
<p align="center">
  <img width="817" height="470" alt="image" src="https://github.com/user-attachments/assets/efdb4622-24d6-4b43-8399-91a1cdaf1dc5" />
</p>

To get access of different domain add this domain to our `/etc/hosts` :
<p align="center">
  <img width="681" height="317" alt="image" src="https://github.com/user-attachments/assets/7bef69e2-e52c-4f1e-855d-30bd6bacdbc9" />
</p>

```
mafialive.thm
```

## 2. Find flag 1
Visit the new domain we just identified and discovered our first flag :
<p align="center">
  <img width="940" height="446" alt="image" src="https://github.com/user-attachments/assets/dd08c683-734c-4674-8a65-60363fa13e28" />
</p>

```
thm{f0und_th3_r1ght_h0st_n4m3}
```

## 3. Look for a page under development
Enumerate the machine using `gobuster` to find more hidden pages :
<p align="center">
  <img width="940" height="370" alt="image" src="https://github.com/user-attachments/assets/4a6290c1-4caa-4b72-ae99-52f63e0e3bd3" />
</p>

Found `robots.txt` visit the page and found the `test.php` page :
<p align="center">
  <img width="940" height="439" alt="image" src="https://github.com/user-attachments/assets/8443c83c-e09b-4c47-84db-b1d09617c925" />
</p>

```
test.php
```

## 4. Find flag 2
Visit the `test.php` page and we can use `view` parameter to get usefull information :
<p align="center">
  <img width="940" height="391" alt="image" src="https://github.com/user-attachments/assets/cac5c4ef-272e-4992-8bdd-6e249386759c" />
</p>

To find the below base64 code we need to use php filter code :
<p align="center">
  <img width="940" height="187" alt="image" src="https://github.com/user-attachments/assets/5dfe787f-fb2e-4e2c-ab33-973621bf7f0d" />
</p>

Decode it using base64 decode and found our flag:
<p align="center">
  <img width="940" height="693" alt="image" src="https://github.com/user-attachments/assets/6d0345e4-f12d-4bb3-8911-ac29623c333e" />
</p>

```
thm{explo1t1ng_lf1}
```

## 5. Get a shell and find the user flag
If we look at the code we can use directory traversal :
<p align="center">
  <img width="419" height="78" alt="image" src="https://github.com/user-attachments/assets/0f4157fa-81d1-4c17-9d4d-043e176eca8f" />
</p>

Using the above information we did Path traversal :
<p align="center">
  <img width="940" height="299" alt="image" src="https://github.com/user-attachments/assets/b7a0e963-a315-45d6-9976-013bc6ce0e73" />
</p>

We started a python server on our local machine to upload reverse shell on target machine :
<p align="center">
  <img width="940" height="147" alt="image" src="https://github.com/user-attachments/assets/7aed4dc2-2a15-45ed-bb81-49858d2f4e03" />
</p>

Successfully uploaded reverse shell on the target machine :

  <img width="940" height="494" alt="image" src="https://github.com/user-attachments/assets/4fdcaeea-c1a4-47c9-bf24-4c740d12f51a" />





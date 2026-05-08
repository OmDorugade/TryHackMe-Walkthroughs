# <div align="center">[Kiba CTF](https://tryhackme.com/room/kiba)</div>
<div align="center">Identify the critical security flaw in the data visualization dashboard, that allows execute remote code execution.
</div>

<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/d8949f9b-8aa8-451b-b2d1-6886cf8ed518" />
</div>

## 1. What is the vulnerability that is specific to programming languages with prototype-based inheritance?
Enumerate the machine using `nmap` :
<p align="center">
  <img width="940" height="888" alt="image" src="https://github.com/user-attachments/assets/fdccf98a-5783-426f-9751-0e5774b7bd70" />
</p>

Search online about the `kibana` and found it is vulnerable to Prototype Pollution 

```
Prototype pollution
```

## 2. What is the version of visualization dashboard installed in the server?
To check the version goto the kibana management page :
<p align="center">
  <img width="808" height="593" alt="image" src="https://github.com/user-attachments/assets/68c7176c-5997-419b-906e-068f503c3845" />
</p>

```
6.5.4
```

## 3. What is the CVE number for this vulnerability? This will be in the format: CVE-0000-0000
Found a gihtub repo and the CVE :
<p align="center">
  <img width="940" height="832" alt="image" src="https://github.com/user-attachments/assets/faae2c35-f9e0-495a-bead-6f765aa9ab44" />
</p>

```
CVE-2019-7609
```

## 4. Compromise the machine and locate user.txt
Enter the payload and run the command,click on canvas and we should have the RCE :
<p align="center">
  <img width="940" height="556" alt="image" src="https://github.com/user-attachments/assets/39d14857-91df-4be6-a9d5-feae4d69dcf6" />
</p>




















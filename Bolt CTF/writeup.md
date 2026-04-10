# <div align="center">[Bolt CTF](https://tryhackme.com/room/bolt)</div>
<div align="center">A hero is unleashed</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/8b4ff6c3-7a43-4cc9-b153-1d339cbdbccb" />
</div>

## 1. What port number has a web server with a CMS running?
<p align="center">
  <img width="756" height="662" alt="image" src="https://github.com/user-attachments/assets/ede79db9-47d0-4654-93f5-630db2fd0476" />
</p>

```
8000
```

## 2. What is the username we can find in the CMS?
<p align="center">
  <img width="825" height="765" alt="image" src="https://github.com/user-attachments/assets/a494d3fe-e95f-447b-b79a-89857605c2f5" />
</p>

```
bolt
```

## 3. What is the password we can find for the username?
<p align="center">
  <img width="653" height="612" alt="image" src="https://github.com/user-attachments/assets/7d28cd41-e78b-4a65-94ef-78fe64532c07" />
</p>

```
boltadmin123
```

## 4. What version of the CMS is installed on the server? (Ex: Name 1.1.1)
Look at the above image in Q2
```
Bolt 3.7.1
```

## 5. There's an exploit for a previous version of this CMS, which allows authenticated RCE. Find it on Exploit DB. What's its EDB-ID?
<p align="center">
  <img width="877" height="631" alt="image" src="https://github.com/user-attachments/assets/943e5080-92e4-4c5d-868d-00d1c531e623" />
</p>

```
48296
```

## 6. Metasploit recently added an exploit module for this vulnerability. What's the full path for this exploit? (Ex: exploit/....)
Steps : 

1.Type `msfconsole` and press enter.

2.Use `search` function to find exploit.

3.Look at the below image : 

<p align="center">
  <img width="903" height="361" alt="image" src="https://github.com/user-attachments/assets/e6a22dd0-9c30-4a22-b1d5-811591444805" />
</p>

```
exploit/unix/webapp/bolt_authenticated_rce
```

## 7. Set the LHOST, LPORT, RHOST, USERNAME, PASSWORD in msfconsole before running the exploit
Follow the steps shown in the images but change it according to your `machine ip` :
<p align="center">
  <img width="903" height="361" alt="image" src="https://github.com/user-attachments/assets/6186e62c-f188-4867-a07d-8825b8d9b24f" />
</p>

Then type `exploit` or `run` to start the exploit.

## 8.Look for flag.txt inside the machine.
<p align="center">
  <img width="827" height="413" alt="image" src="https://github.com/user-attachments/assets/1c495b42-2562-4687-bfd8-2753130c347b" />
</p>

```
THM{wh0_d035nt_l0ve5_b0l7_r1gh7?}
```

Room Completed


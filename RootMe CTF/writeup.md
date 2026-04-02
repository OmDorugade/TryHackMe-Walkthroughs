# <div align="center">[RootMe](https://tryhackme.com/room/rrootme)</div>
<div align="center">A ctf for beginners, can you root me?</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/1cb76a5b-fe2c-4b1e-9719-3f27dfd1993d" />
</div>

## 1. Deploy the machine  
<p align="center">
  <img width="940" height="527" alt="image" src="https://github.com/user-attachments/assets/55336a8e-d580-4a8b-9377-909429c26eb0" />
</p>
  
```
No answer needed  
```

## 2. Scan the machine, how many ports are open?
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/02312991-eaa1-40fd-88d0-8e1efd88299e" />
</p>
  
```
2
```

## 3.What version of Apache is running?
```
2.4.41
```

## 4. What service is running on port 22?
```
ssh
```

## 5. Find directories on the web server using the GoBuster tool.
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/bea84bb9-a683-47c5-9165-c6f727f25879" />
</p>

```
No answer needed
```

## 6. What is the hidden directory?
```
/panel
```

## 7. Find a form to upload and get a reverse shell, and find the flag.
We can upload phtml files on `/uploads` directory.

1.Upload phtml file with a reverse shell.

2.Set up a listner on our machine.

3.Click on the file that we uploaded i.e `phtml`.

4.We will get a reverse shell.

user.txt
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/efbd499f-1a8c-49ed-a82c-3c0b49b70c17" />
</p>

```
THM{y0u_g0t_a_sh3ll}
```

## 8. Search for files with SUID permission, which file is weird?
<p align="center">
  <img width="288" height="166" alt="image" src="https://github.com/user-attachments/assets/9f17ceab-d17a-4626-ac07-29c0e50e17f1" />
</p>

```
/usr/bin/python
```

## 9. Find a form to escalate your privileges.
<p align="center">
  <img width="940" height="516" alt="image" src="https://github.com/user-attachments/assets/03370ccf-ec84-4308-92c4-b9f666b3abe9" />
</p>

```
No answer needed
```

## 10. Root.txt
<p align="center">
  <img width="443" height="127" alt="image" src="https://github.com/user-attachments/assets/89cfba0f-135f-4726-a704-918dea32c903" />
</p>

```
THM{pr1v1l3g3_3sc4l4t10n}
```


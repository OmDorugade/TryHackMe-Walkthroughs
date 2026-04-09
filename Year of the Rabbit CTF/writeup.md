# <div align="center">[Year of the Rabbit CTF](https://tryhackme.com/room/yearoftherabbit)</div>
<div align="center">Time to enter the warren...</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/45af5007-f1d4-41eb-9d38-c0775f4cfad7" />
</div>

## 1. What is the user flag?
Use `gobuster` to find directories : 
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/fea68f06-88aa-47be-b455-a02b8d0c0138" />
</p>

Check the `style.css` file :
<p align="center">
  <img width="695" height="755" alt="image" src="https://github.com/user-attachments/assets/8c42a039-243d-4c9f-86b9-28a82c8da6d4" />
</p>

Lets take look at the `/sup3r_s3cret_fl4g/` :
<p align="center">
  <img width="940" height="875" alt="image" src="https://github.com/user-attachments/assets/9d8b05bb-903f-4aeb-ba88-9e6eb4e84c22" />
</p>

Searched online about this and followed this steps :

1.I am using `firefox` browser we need to type `about:config` 

2.Search about `javascript.enabled`

3.Make it `false`
<p align="center">
  <img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/893ddf31-7713-4e90-91f4-413fff572f44" />
</p>

4.Reload the page and use `Burpsuite` to capture the response for a new directory :
<p align="center">
  <img width="940" height="600" alt="image" src="https://github.com/user-attachments/assets/07451231-576f-4688-ac93-8c9d88287700" />
</p>

Visit the directory we got a new file , Just use `cat` and the file name :














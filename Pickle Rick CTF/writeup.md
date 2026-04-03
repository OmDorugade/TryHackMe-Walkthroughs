# <div align="center">[Pickle Rick](https://tryhackme.com/room/picklerick)</div>
<div align="center">A Rick and Morty CTF. Help turn Rick back into a human!</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/11680573-eff1-4d0c-ac75-76e89c84b708" />
</div>

This Rick and Morty-themed challenge requires you to exploit a web server and find three ingredients to help Rick make his potion and transform himself back into a human from a pickle.

Deploy the virtual machine on this task and explore the web application

## 1. What is the first ingredient that Rick needs?

Checking the page-source of the website and we found a username

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/34ab5307-cba6-4962-b8b5-22d8f5194439" />
</p>

Checking the `robots.txt` file we found this !
<p align="center">
  <img width="238" height="50" alt="image" src="https://github.com/user-attachments/assets/14f6fce9-f3df-4aaf-8c87-68a32d0ea0ce" />
</p>

Used `gobuster` for directory traversal 
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/9d7793cb-4f13-427b-9b3d-7100cbe0fbb7" />
</p>

```
mr. meeseek hair
```













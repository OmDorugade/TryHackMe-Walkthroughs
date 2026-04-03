# <div align="center">[Pickle Rick](https://tryhackme.com/room/picklerick)</div>
<div align="center">A Rick and Morty CTF. Help turn Rick back into a human!</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/11680573-eff1-4d0c-ac75-76e89c84b708" />
</div>

This Rick and Morty-themed challenge requires you to exploit a web server and find three ingredients to help Rick make his potion and transform himself back into a human from a pickle.

Deploy the virtual machine on this task and explore the web application.

## 1. What is the first ingredient that Rick needs?

Checking the page-source of the website and we found a username

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/34ab5307-cba6-4962-b8b5-22d8f5194439" />
</p>

Checking the `robots.txt` file we found this !
<p align="center">
  <img width="238" height="50" alt="image" src="https://github.com/user-attachments/assets/14f6fce9-f3df-4aaf-8c87-68a32d0ea0ce" />
</p>

Used `gobuster` for directory traversal.
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/9d7793cb-4f13-427b-9b3d-7100cbe0fbb7" />
</p>

Now if we look again at the files under `/assets`, we see a `portal.jpg`.

Found a login page `portal.php` and using the username as `R1ckRul3s` and password as `Wubbalubbadubdub` we were logged in.
<p align="center">
  <img width="1457" height="616" alt="image" src="https://github.com/user-attachments/assets/2748e442-0021-4931-8407-6ec516a6716e" />
</p>

Used `ls` in the command panel we found a text file but we cannot use `cat` command so searched another command for `cat` and found `less` command.
<p align="center">
  <img width="1447" height="446" alt="image" src="https://github.com/user-attachments/assets/41d83377-9a58-4063-b5ca-bf11bc9705e6" />
</p>

<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/2b4c1a17-8d4d-441f-9b91-4b6a282699ea" />
</p>

```
mr. meeseek hair
```

Now we try to get the source PHP code to get a list of all the blacklisted commands. We put in `grep -R " "` in the command box and get the following page as output :
<p align="center">
  <img width="1122" height="891" alt="image" src="https://github.com/user-attachments/assets/f7a845f0-31d5-485e-a08e-360ea2dfaedb" />
</p>

Inspecting the source, we get the list of the blacklisted command as follows :
<p align="center">
  <img width="1628" height="292" alt="image" src="https://github.com/user-attachments/assets/472bc138-2dd1-4701-a425-6df3a447d371" />
</p>

## 2. What is the second ingredient in Rick’s potion?

We are able to run `sudo -l` command so we did that and went to this directory `/home/rick/second ingredients` to get second flag and got this:
<p align="center"> 
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/5574d254-fb63-4617-90a0-4791acf8d329" />
</p>

```
1 jerry tear
```

## 3. What is the last and final ingredient?

We Found the third ingredient in the `/root/3rd.txt` and got the final flag:
<p align="center">
  <img width="940" height="506" alt="image" src="https://github.com/user-attachments/assets/3625522d-e411-47bb-b906-91499d7ad75f" />
</p>

```
fleeb juice
```

Room Completed!

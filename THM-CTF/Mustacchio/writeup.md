# <div align="center">[Mustacchio](https://tryhackme.com/room/mustacchio)</div>
<div align="center">Easy boot2root Machine.</div>

<div align="center">
  <img width="250" height="250" alt="image" src="https://github.com/user-attachments/assets/b77af3be-fc9d-4957-85fd-f397d1a0970e" />
</div>

## 1. What is the user flag?
Enumerate the machine using `nmap` :
<p align="center">
  <img width="940" height="471" alt="image" src="https://github.com/user-attachments/assets/22a232ee-5e73-4919-8812-75b197af85cc" />
</p>

Using `gobuster` we did directory enumeration :
<p align="center">
  <img width="940" height="468" alt="image" src="https://github.com/user-attachments/assets/15c94a48-919c-48f0-a084-03db10ff9159" />
</p>

We have found different paths checking `/custom` page :
<p align="center">
  <img width="940" height="696" alt="image" src="https://github.com/user-attachments/assets/0a7c7a62-1ba4-4d30-90c9-d32a354d070f" />
</p>

Checking the `user.bak` file we found MD5 Hash and crack it using CrackStation :
<p align="center">
  <img width="940" height="370" alt="image" src="https://github.com/user-attachments/assets/57b3acd0-857e-4c30-8f9f-b69d86438118" />
</p>

Looking at the nmap result we have ngnix running on 8765 port and found admin panel :
<p align="center">
  <img width="940" height="643" alt="image" src="https://github.com/user-attachments/assets/89f4e636-e839-4322-9830-29f3d104575a" />
</p>

Checking the source code of admin panel page we got this :
<p align="center">
  <img width="940" height="548" alt="image" src="https://github.com/user-attachments/assets/cc4516ff-bb2a-4e4e-b85f-0e7dd1eaad16" />
</p>

We then found Comment section and used XML External Entity (XXE) injection :
<p align="center">
  <img width="940" height="564" alt="image" src="https://github.com/user-attachments/assets/68844581-16c9-4ef5-86d3-4596ec699cb8" />
<



















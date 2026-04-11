# <div align="center">[Wgel CTF](https://tryhackme.com/room/wgelctf)</div>
<div align="center">Can you exfiltrate the root flag?</div>
<br>
<div align="center">
  <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/cd7d2590-9942-4adc-adf0-4bedf12c695e" />
</div>

## 1. User flag
Performed `nmap` for port-scanning and `gobuster` to find hidden diretories :
<p align="center">
  <img width="827" height="660" alt="image" src="https://github.com/user-attachments/assets/94bb1419-312d-4a65-87b8-8636c9a6747f" />
</p>

Then visit the `source code` of the website and found this :
<p align="center">
  <img width="965" height="611" alt="image" src="https://github.com/user-attachments/assets/f5745900-0928-4f1e-85ca-926a0f5f1e55" />
</p>

Lets visit the `sitemap` and further enumerated this page :
<p align="center">
  <img width="1242" height="583" alt="image" src="https://github.com/user-attachments/assets/10b8156e-e792-406d-a46b-9b2662a8fa65" />
</p>

We know that in `.ssh` folder we may found someones `RSA Private Key` :
<p align="center">
  <img width="626" height="781" alt="image" src="https://github.com/user-attachments/assets/938299c1-328e-4b0e-ad45-eeb48d59b390" />
</p>

Copy paste the `id_rsa` and give permissions and log in using `ssh` :
<p align="center">
  <img width="868" height="620" alt="image" src="https://github.com/user-attachments/assets/5ff66b2b-df88-4926-ac36-a7c92c901673" />
</p>

Finally found the `user flag` : 
<p align="center">
  <img width="757" height="123" alt="image" src="https://github.com/user-attachments/assets/f9968f83-b1e7-4564-a34b-38aded5c2ba1" />
</p>

```
057c67131c3d5e42dd5cd3075b198ff6
```

## 2. Root flag
We used `sudo -l` and found this :
<p align="center">
  <img width="737" height="121" alt="image" src="https://github.com/user-attachments/assets/9e459671-f800-464b-b99c-35e359373da9" />
</p>

Use `gftobin` to find more about how we can exploit this :
<p align="center">
  <img width="1068" height="542" alt="image" src="https://github.com/user-attachments/assets/b25bc4f2-7519-4b31-8b99-4945cb1e32bd" />
</p>

Use the command but before using it set up a listener on our machine :
<p align="center">
  <img width="851" height="87" alt="image" src="https://github.com/user-attachments/assets/d8b6f5b1-6d9d-4928-bc1e-a4eaa13f38fe" />
</p>

Set up the listener and type the above command shown in image and we got our `root flag` :
<p align="center">
  <img width="697" height="470" alt="image" src="https://github.com/user-attachments/assets/05956299-cb05-49c4-a466-dd7d40bfc513" />
</p>

```
b1b968b37519ad1daa6408188649263d
```

Room Completed !





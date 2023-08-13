# Kepper

10.129.96.139

## NMAP (Top 1k)

```bash
PORT   STATE SERVICE REASON         VERSION
22/tcp open  ssh     syn-ack ttl 63 OpenSSH 8.9p1 Ubuntu 3ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 3539d439404b1f6186dd7c37bb4b989e (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBKHZRUyrg9VQfKeHHT6CZwCwu9YkJosNSLvDmPM9EC0iMgHj7URNWV3LjJ00gWvduIq7MfXOxzbfPAqvm2ahzTc=
|   256 1ae972be8bb105d5effedd80d8efc066 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIBe5w35/5klFq1zo5vISwwbYSVy1Zzy+K9ZCt0px+goO
80/tcp open  http    syn-ack ttl 63 nginx 1.18.0 (Ubuntu)'' 
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

## Port 80 Webserver
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    
```html
<html>
  <body>
    <a href="http://tickets.keeper.htb/rt/">To raise an IT support ticket, please visit tickets.keeper.htb/rt/</a>
  </body>
</html>
```

* keeper.htb, tickets.keeper.htb added to /etc/hosts
* No additional subdomains found.
* Default creds work - root:password

Found users in admin panel:
* lnorgaard - lnorgaard@keeper.htb
* If you scroll down to the comments for the user lnorgaard there is a clear text password - Welcome2023!

## Initial foothold & Enumeration

The username and password above work for SSH.

### linPEAS

```bash
╔══════════╣ Active Ports
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#open-ports                                                                                          
tcp        0      0 127.0.0.1:25            0.0.0.0:*               LISTEN      -                                                                                      
tcp        0      0 127.0.0.1:9000          0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:3306          0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp6       0      0 ::1:25                  :::*                    LISTEN      -                   
tcp6       0      0 :::22                   :::*                    LISTEN      -                   
tcp6       0      0 :::80                   :::*                    LISTEN      -
```

```bash
╔══════════╣ Superusers
root:x:0:0:root:/root:/bin/bash                                                                                                                                        

╔══════════╣ Users with console
lnorgaard:x:1000:1000:lnorgaard,,,:/home/lnorgaard:/bin/bash                                                                                                           
root:x:0:0:root:/root:/bin/bash
```

```bash
╔══════════╣ Searching root files in home dirs (limit 30)
/home/                                                                                                                                                                 
/home/lnorgaard/user.txt
/home/lnorgaard/.vimrc
/home/lnorgaard/.bash_history
/home/lnorgaard/RT30000.zip
/root/
/var/www
/var/www/html
/var/www/html/index.html
```

* Not much found with linPEAS.

## Privilege Escalation

* Inside of the users /home there is a zip file that contains two KeePass files.
* The two files are a dump file and a KeePass database.
* There is a vulnerability for KeePass https://nvd.nist.gov/vuln/detail/cve-2023-32784
* There are several PoCs for this vulnerability, this one seems to work best: https://github.com/vdohney/keepass-password-dumper
* Run the tool against the dump file and it finds a result, although this is not the password. But upon google searching the password there is an interesting result:

```html

Rødgrød med Fløde - Receta Tradicional Danesa
196 flavors
https://www.196flavors.com › rodg...
Oct 29, 2021 — El rødgrød med fløde es un postre clásico del verano danés hecho con bayas del bosque, azúcar, vainilla y nata.
```
* rødgrød med fløde is the password to the KeePass database.

* After opening the database (I used KeePassXC) there is an entry under 'Network' with a note that says "PuTTY-User-Key-File3"
* Inside of this file there is a PuTTY SSH key. Copy and paste this into a file and give it the .ppk extension. This will have to be converted
* Googling this process, the first link has the info we need (https://tecadmin.net/convert-ppk-to-pem-using-command/)

```bash
puttygen wot.ppk -O private-openssh -o root-key.pem
```

* This will generate the SSH key for the root user! :DDD

```bash
chmod 600 root-key.pem
ssh -i root-key.pem root@keeper.htb
```

GG :)
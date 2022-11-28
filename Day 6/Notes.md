##### Nmap Script Scan Types:
```
    safe:- Won't affect the target
    intrusive:- Not safe: likely to affect the target
    vuln:- Scan for vulnerabilities
    exploit:- Attempt to exploit a vulnerability
    auth:- Attempt to bypass authentication for running services (e.g. Log into an FTP server anonymously)
    brute:- Attempt to bruteforce credentials for running services
    discovery:- Attempt to query running services for further information about the network (e.g. query an SNMP server).
```

##### Nmap default Scripts 
```
/usr/share/nmap/scripts/script.db
```

##### Firewall Evasion With Nmap
```
##### Nmap SYN Scan
During this scan only half packet is sent and reset flag is sent at end. This allows attacker to bypass old IDS.

-pN [Continues Scanning even if the host is not responding to ICMP packet]
-f [Breaks packet into fragments of Packets]
--scan-delay <time>ms [USeful if the network is unstable]
```

##### Privilege Escalation Via Python Library Hijacking
```
Vulnerable script
import hashlib

def hashing(passw):

    md5 = hashlib.md5(passw.encode())

    print("Your MD5 hash is: ", end ="")
    print(md5.hexdigest())

    sha256 = hashlib.sha256(passw.encode())

    print("Your SHA256 hash is: ", end ="")
    print(sha256.hexdigest())

    sha1 = hashlib.sha1(passw.encode())

    print("Your SHA1 hash is: ", end ="")
    print(sha1.hexdigest())


def main():
    passw = input("Enter a password to hash: ")
    hashing(passw)

if __name__ == "__main__":
    main()


```

Here, we dont have write permission on the script.py file but have write perm in the library hashlib

##### sudo PYTHONPATH=/tmp/ /usr/bin/python3 /home/hazel/hasher.py

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
-pN [Continues Scanning even if the host is not responding to ICMP packet]
```

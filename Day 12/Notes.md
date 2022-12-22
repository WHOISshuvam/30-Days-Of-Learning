#### Stages of Penetration Test

>While performing tests minimal impact must be done on clients system and network.

Engagement | Information Gathering | Footprinting | Vulnerability Assesement | Exploitation | Reporting
| --- | --- | --- | --- | --- | ---|

##### Information Gathering
* Perform OSINT on Companies Social Networking Sites like linkedin, twitter, crunchbase to enumerate emails, PII of employee working on target company.
* Enumerate information using whois lookup.
* Lets assume we got raj.gurungcompany.tld as email, using the same pattern we can enumerate other users emails.

##### Footprinting
- Ping Sweep Scan
- fping 
```
usage : fping -a -g IP/NETMASK / IP - IP
-a alive hosts
-g ping sweep scan

fping -a -g 192.168.0.1 192.168.0.255 2>/dev/null Supress Errors
```

#### p0f 
```
pof -i eth0 -o output.txt
```
---

#### Vulnerability Assesement VS Penetration Testing

>VA is a part of PT.

>VA imposes lighter weight on the infrastructure.

> Confirmation of Vulnerability is not required in VA.
---

#### Nmap Version Detection

![Screenshot at 2022-12-22 14-44-44](https://user-images.githubusercontent.com/85208639/209098921-2af29781-47ea-49b8-9856-e03d8e035824.png)

#### Input Format Supported 
```
nmap scantype 192.168.1.45 200.200.14.56 10.10.10.1
nmap scantype 10.0.0.0/8
nmap scantype 192.168.0.*
nmap scantype 192.168.7-233.*
nmap scantype 10.14.33.1,2,255,10
```

#### Firewall Detection:

```
34000/tcp open tcpwrapped
```
> This indicates that 3 way handshake was successful but the remote host closed the connection without receiving data.

#### Notes :
> Scope : IP Address, Network Block, Domain Names 

> Only after legal documents are signed the penetration test should be performed.


> Collect information about employees, company location, board of directors. Extracted information can be used for social engineering if allowed in ROE.


> For eg. if the scope is whole company collect CIDR, ips, domains, try zone transfer, find live hosts, enumerate web servers, operating system.


> Use information collected in previous step perform portscan, directory bruteforce, use automated tools like burp, nikto, openvas, nexpose, nessus, to find scan hosts.


> Perform mannual testing side by side.


>Try exploiting vulnerabilties identified in previous step and finally the report is created.


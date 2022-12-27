
#### Nmap Scan And Dir Fuzz :

```
Discovered open port 80/tcp on 192.189.153.3
Discovered open port 8000/tcp on 192.189.153.3
Discovered open port 5000/tcp on 192.189.153.3

```

#### Directory FUZZ

```
http://192.189.153.3:8000/console  >> Password Protected

http://192.189.153.3:8000/.git/config

[user]
	name = Jeremy McCarthy
	email = jeremy@dummycorp.com
	password = diamonds
	username = jeremy

http://192.189.153.3:8000/.git/index

```
```
git log
```
![Screenshot at 2022-12-27 13-26-48](https://user-images.githubusercontent.com/85208639/209631482-a7d5a943-9f96-4f8b-933a-7a78e9a9127b.png)

```
git diff commit >> See Changes
```
![Screenshot at 2022-12-27 13-35-51](https://user-images.githubusercontent.com/85208639/209632642-a2936fab-6c6e-42cf-bac8-4b91535c4dec.png)

![Screenshot at 2022-12-27 13-42-34](https://user-images.githubusercontent.com/85208639/209633513-113d681e-7aab-4b0c-b748-15c36d67df2c.png)




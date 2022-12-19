#### Forward Connection
>The following command creates a link to a local port 8000 with remote host 172.16.0.10 running on port 80 utilizing the SSH access on 172.16.0.5. "-fN" flag allows us to background the shell (f) and not to execute any command after connection.
```
ssh -L localhost:8000:172.16.0.10:80 user@172.16.0.5 -fN
```

>Demo:
https://www.youtube.com/watch?v=F-ubwghsWPM

#### Create Proxies 
```
ssh -D 1337 user@ip -fN
```

#### Reverse SSH Tunneling:

![Screenshot at 2022-12-19 15-09-44](https://user-images.githubusercontent.com/85208639/208393964-1f4c4f53-e28b-493d-8b28-812d65d5d516.png)

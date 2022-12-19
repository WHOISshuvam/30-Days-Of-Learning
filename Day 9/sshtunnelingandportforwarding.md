#### Forward Connection
>The following command creates a link to a local port 8000 with remote host 172.16.0.10 running on port 80 utilizing the SSH access on 172.16.0.5. "-fN" flag allows us to background the shell (f) and not to execute any command after connection.
```
ssh -L 8000:172.16.0.10:80 user@172.16.0.5 -fN
```

#### Create Proxies 
```
ssh -D 1337 user@ip -fN
```

>Resource:
https://www.youtube.com/watch?v=F-ubwghsWPM

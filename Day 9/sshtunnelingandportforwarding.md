>The following command creates a link to a local port 8000 with remote host 172.16.0.10 running on port 80 utilizing the SSH access on 172.16.0.5.
```
ssh -L 8000:172.16.0.10:80 user@172.16.0.5 -fN
```

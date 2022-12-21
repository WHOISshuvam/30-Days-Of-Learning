##### Copying files between ssh server and local machine
scp -i id_rsa localfile root@remoteip:/home/Desktop/directory/localfile

##### Mannually add and delete ip routes
```
sudo ip route add 192.168.222.0/24  via 10.175.34.1  

sudo ip del add 192.168.222.0/24  via 10.175.34.1  
```

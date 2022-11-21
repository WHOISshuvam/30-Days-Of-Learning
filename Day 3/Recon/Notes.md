
### Virtual Host Fuzzing 
Virtual Host is used to host multiple domain names under same web-server. If one IP contains more than one virtual hosts then virtual hosts can be accessed by sending the correct host name in the HOST header. If the internal sites of a company is hosted on same web-server publicly, then user may be able to access the internal site via sending appropriate host in header.

#### Lets say we are given a range 69.63.176.0/23 to test and we found following 3 hosts alive.

69.63.177.224
69.63.177.58
69.63.176.3

#### Reverse DNS Lookup 
69.63.177.224 hello.fb.com
69.63.177.58  testprep.fb.com
69.63.176.3   *.qq.fb.com staging.fb.com qa.prod.fb.com

##### ( Multiple vhost are hosted under 69.63.176.3 )

### Subdomain Enumeration of qq.fb.com gives following result.
sandbox.qq.fb.com
marky.qq.fb.com
prod-marky.qq.fb.com

##### FUZZ the above subdomains as vhost on 69.63.176.3 >> We might me able to access internal hosts.



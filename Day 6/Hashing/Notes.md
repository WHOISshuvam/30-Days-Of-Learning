##### Cracking hashes:
```
john --format=format --wordlist=rockyou.txt hash.txt
```

##### List hash format:
```
john --list=formats
```

##### Alternative [Hashcat]
```
hashcat -m mode /tmp/words.txt hash.txt
```

##### List hash format:
```
hashcat --help | grep hash
```

##### Crack /etc/shadow files
```
john --format=sha512crypt --wordlist=/usr/share/wordlists/rockyou.txt etchashes.txt 
```

##### Cracking Hashes Without Password Wordlist 
```
Content of hash.txt
arpan:hash
Here john creates its own wordlist based on the username like 4rp4n, aRpAn, etc.
john --single --format=format hash.txt
```

##### Cracking password protected Zip Files with john
```
zip2john hello.zip > hi.txt
john --wordlist=pass.txt hi.txt
```

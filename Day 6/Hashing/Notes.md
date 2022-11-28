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

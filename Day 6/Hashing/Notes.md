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

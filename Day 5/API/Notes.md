##### Check throughly the requests when editing user details for cross account updates, fetching information.
##### Try modifying cookies, headers, jwt token testing others account.

##### Bruteforce Weak jwt secret with hashcat 
```
hashcat -m 16500 jwttoken.txt rockyou.txt
```

##### Always check js files for endpoints, functions that maynot be available as a normal user

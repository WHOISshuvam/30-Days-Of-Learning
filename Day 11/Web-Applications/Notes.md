#### Connect with HTTPS Server Using Openssl
```
openssl s_client -connect host:port

openssl s_client -connect host:port --debug

```

<!--Netscape created cookies for the first time to make HTTP stateful -->

#### Sessions

>Websites at server side store client information as sessionid and each user is assigned a separate session id.
>Websites using PHP typically use PHPSESSID while those using jsp use "JSESSIONID"

>Note:Session Cookies expires once the browser is closed.

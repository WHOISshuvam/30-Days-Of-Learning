#### Sending HTTP requests in ruby
###### docker run -it ruby /bin/bash
```
$gem install httparty
$irb //lets us exec commands without creating a file
require 'httparty'
HTTParty.get("http://localhost/search", query: {'q: apple'} )
HTTParty.get("http://localhost/search", headers: {'Cookie': 'aaa=biscuit'})
```

###### POST request with parameters and Headers
```
require 'httparty'
HTTParty.post("http://localhost/search", {body: "q=apple"} )
HTTParty.post("http://localhost/search", {body: "q=apple", headers: {'User-Agent': 'Pentest'}}) 
```

###### URL encode decode 
require 'uri'; str="%2500" ; puts URI.decode(str);

##### Send HTTP multipart request using curl
```
curl http://localhost -F  "file_parameter=@localfile.txt' --trace-ascii -
```

##### Testing Directory Traversal vulnerabilities during file upload using curl
```
curl http://localhost -F "filename=@localfile.txt;filename=../../../etc/passwd"
```

##### Sending a Basic Auth Request
curl http://localhost/admin -u admin:password

##### Send a yaml body with array with multiple values
```
curl "http://localhost/upload" -X POST -H 'Content-Type: application/yaml' --data-binary @yaml.txt
Content of yaml.txt
key:
  - value1
  - value2
```

##### Sometimes sending same parameters twice can bypass simple filterings

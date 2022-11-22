#### Sending HTTP requests in ruby
##### docker run -it ruby /bin/bash

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
##### Sometimes sending same parameters twice can bypass simple filterings

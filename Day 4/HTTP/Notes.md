#### Sending HTTP requests in ruby
##### docker run -it ruby /bin/bash

```
$gem install httparty
$irb //lets us exec commands without creating a file
require 'httparty'
HTTParty.get("http://localhost/search", query: {'q: apple'} )
HTTParty.get("http://localhost/search", headers: {'Cookie': 'aaa=biscuit'})
```

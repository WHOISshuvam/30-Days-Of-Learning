#### Sending HTTP requests in ruby
##### docker run -it ruby /bin/bash

```
$gem install httparty
$irb //lets us exec commands without creating a file
require 'httparty'
HTTParty.get("http://ptl-5342b892-53659fe2.libcurl.so/pentester", query: {'key=please'} )

```

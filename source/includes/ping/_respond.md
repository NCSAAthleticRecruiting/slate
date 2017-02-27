# RESPOND/PING

**GET `/api/team_edition/ping`**

Health Check for Team Edition application

**Code Examples**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/ping")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  "http://qa.ncsasports.org/api/team_edition/ping"
```



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

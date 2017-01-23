## Get an Organization's Athletes

> Sample Successful Request:

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/9/athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/9/athletes")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

GET for retrieving all athlete resources from an organization

### HTTP Request

`GET /api/team_edition/organizations/[:organization_id]/athletes`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

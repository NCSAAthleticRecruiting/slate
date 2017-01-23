## Update an Organization

> Sample Request Body

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "Test Club Uno",
      "zip-code": "60642",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "clubtest@ncsasports.tst",
      "phone": "1234567899",
      "website": "http://www.example.com",
      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"
    }
  }
}
```

> Sample Successful Request

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/organizations/9 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{\n  "data": {\n    "type": "organizations",\n    "attributes": {\n      "name": "Test Club Uno",\n      "zip-code": "60642",\n      "address": "234 Maple Lane",\n      "city": "Chicago",\n      "state": "IL",\n      "email": "clubtest@ncsasports.tst",\n      "phone": "1234567899",\n      "website": "http://www.example.com",\n      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"\n    }\n  }\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/9")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request.body = "{\n  \"data\": {\n    \"type\": \"organizations\",\n    \"attributes\": {\n      \"name\": \"Test Club Uno\",\n      \"zip-code\": \"60642\",\n      \"address\": \"234 Maple Lane\",\n      \"city\": \"Chicago\",\n      \"state\": \"IL\",\n      \"email\": \"clubtest@ncsasports.tst\",\n      \"phone\": \"1234567899\",\n      \"website\": \"http://www.example.com\",\n      \"logo-url\": \"//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg\"\n    }\n  }\n}"

response = http.request(request)
puts response.read_body
```

PATCH for  an organization resource

### HTTP Request

`PATCH /api/team_edition/organizations/[:organization_id]`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

## Get an Organization

> Sample Successful Request

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/9 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{\n  "data": {\n    "type": "sessions",\n	  "attributes": {\n	    "email": "jlockhart@ncsasports.org",\n	    "password": "password"\n	 }\n  }\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/9")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request.body = "{\n  \"data\": {\n    \"type\": \"sessions\",\n\t  \"attributes\": {\n\t    \"email\": \"jlockhart@ncsasports.org\",\n\t    \"password\": \"password\"\n\t }\n  }\n}"

response = http.request(request)
puts response.read_body
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "1",
    "type": "organizations",
    "attributes": {
      "name": "Cool Volleyball",
      "zip-code": "56906",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "org@example.com",
      "phone": "3122234567",
      "website": "http://www.example.com",
      "logo-url": "/images/default_organization_image.png",
      "current-contract-ids": [4],
      "sports": [
        "Women's Volleyball",
        "Men's Volleyball"
      ],
      "primary-contact-name": null
    },
    "links": {
      "self": "/api/team_edition/organizations/1"
    }
  },
  "links": {
    "self": "/api/team_edition/organizations/1"
  }
}

```

GET for retrieving organization resource

### HTTP Request

`GET /api/team_edition/organizations/[:organization_id]`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

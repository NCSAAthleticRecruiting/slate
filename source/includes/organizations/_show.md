# Show Organization
<br>

## _Overview_

* `GET /api/team_edition/organizations/[:organization_id]`
* Request Headers
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": {
    "id": "1",
    "type": "organizations",
    "attributes": {
      "name": "Spree Volleyball",
      "zip-code": "56906",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "org@example.com",
      "phone": "3122234567",
      "website": "http://www.example.com",
      "logo-url": "/images/default_organization_image.png",
      "current-contract-ids": [],
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

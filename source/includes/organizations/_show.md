# GET AN ORGANIZATION

**GET `/api/team_edition/organizations/:organization_id`**

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```



## Responses

**Sample Successful Response**

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

## Errrors/Statuses

See relevant spec files.

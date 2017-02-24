# Show All Pricing Tier Sports

**GET `/api/team_edition/pricing_tier_sports`**

This endpoint shows all of the pricing tier sports.

### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Request

**cURL**

```shell
curl --request GET \
  --url http:/qa.ncsasports.org/api/team_edition/pricing_tier_sports \
  --header 'content-type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \

```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http:/qa.ncsasports.org/api/team_edition/pricing_tier_sports")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request['content-type'] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


### Sample Response

```json
{
  "data": [
    {
      "id": "1",
      "type": "sports",
      "attributes": {
        "name": "lacrosse",
        "display-name": "Lacrosse"
      }
    },
    {
      "id": "2",
      "type": "sports",
      "attributes": {
        "name": "volleyball",
        "display-name": "Volleyball"
      }
    },
    {
      "id": "3",
      "type": "sports",
      "attributes": {
        "name": "soccer",
        "display-name": "Soccer"
      }
    },
    {
      "id": "4",
      "type": "sports",
      "attributes": {
        "name": "field_hockey",
        "display-name": "Field Hockey"
      }
    },
    {
      "id": "5",
      "type": "sports",
      "attributes": {
        "name": "softball",
        "display-name": "Softball"
      }
    },
    {
      "id": "6",
      "type": "sports",
      "attributes": {
        "name": "baseball",
        "display-name": "Baseball"
      }
    },
    {
      "id": "7",
      "type": "sports",
      "attributes": {
        "name": "basketball",
        "display-name": "Basketball"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/pricing_tier_sports"
  }
}


```

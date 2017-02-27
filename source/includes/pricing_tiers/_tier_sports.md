# SHOW ALL PRICING TIER SPORTS

**GET `/api/team_edition/pricing_tier_sports`**

This endpoint shows all of the sports with pricing tiers.


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
  "http:/qa.ncsasports.org/api/team_edition/pricing_tier_sports" \
  --header 'content-type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
```

<br>

_Ruby Net::HTTP_

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


## Responses

**Sample Response Body**

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



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

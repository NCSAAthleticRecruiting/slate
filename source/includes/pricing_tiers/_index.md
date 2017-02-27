# GET ALL PRICING TIERS FOR SPORT

**GET `/api/team_edition/sports/:sport_id/pricing_tiers`**

This endpoint shows all the possible pricing tiers for a given sport.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Samples**

_cURL_

```shell
curl --request GET \
  "http://qa.ncsasports.org/api/team_edition/sports/1/pricing_tiers" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'

```

_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/sports/1/pricing_tiers")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```

## Responses

**Response Types**

| Status Code                    | Description/Cause                 |
|--------------------------------|-----------------------------------|
| 200 OK                         | Successfully retrieved teams      |


**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "1",
      "type": "pricing-tiers",
      "attributes": {
        "max-athletes": 25,
        "min-teams": 1,
        "max-teams": 4,
        "price": "230.0"
      },
      "relationships": {
        "sport": {
          "data": {
            "id": "1",
            "type": "sports"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "pricing-tiers",
      "attributes": {
        "max-athletes": 25,
        "min-teams": 5,
        "max-teams": 9,
        "price": "205.0"
      },
      "relationships": {
        "sport": {
          "data": {
            "id": "1",
            "type": "sports"
          }
        }
      }
    },
    {
      "id": "3",
      "type": "pricing-tiers",
      "attributes": {
        "max-athletes": 25,
        "min-teams": 10,
        "max-teams": 100,
        "price": "180.0"
      },
      "relationships": {
        "sport": {
          "data": {
            "id": "1",
            "type": "sports"
          }
        }
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/sports/1/pricing_tiers"
  }
}
```

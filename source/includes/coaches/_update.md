# Update Coach
<br>

## _Overview_

`PATCH /api/team_edition/coaches/[:coach_id]`

_Request Headers_
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`
_Sample Request Body (to change last name from "Hamm" to "HaMm-Wow")_

```json
{
  "data": {
    "attributes": {
      "last_name": "Hamm-Wow"
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "1",
          "type": "organizations"
        }
      },
      "team": {
        "data": [
          {
            "id": "3",
            "type": "teams"
          }
        ]
      }
    },
    "type": "coaches"
  }
}

```

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/coaches/2 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"coaches","attributes":{"last_name":"Hamm-Wow"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"team":{"data":[{"type":"teams","id":"3"}]}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/coaches/2")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"coaches\",\"attributes\":{\"last_name\":\"Hamm-Wow\"},\"relationships\":{\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"1\"}},\"team\":{\"data\":[{\"type\":\"teams\",\"id\":\"3\"}]}}}}"

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": {
    "id": "2",
    "type": "coaches",
    "attributes": {
      "first-name": "Mia",
      "last-name": "Hamm-Wow",
      "email": "mia@example.com",
      "phone": "",
      "position-title": "Head Coach",
      "photo-url": "/images/default_user_image.png",
      "admin": true,
      "deleted": false
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "1",
          "type": "organizations"
        }
      },
      "teams": {
        "data": [
          {
            "id": "3",
            "type": "teams"
          }
        ]
      }
    },
    "links": {
      "self": "/api/team_edition/coaches/2"
    }
  }
}
```

## Errors & Statuses

* For errors, see relevant spec files.

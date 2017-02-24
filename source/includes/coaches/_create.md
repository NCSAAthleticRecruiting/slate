# Create Coach
<br>

## _Overview_

`POST /api/team_edition/organizations/[:organization_id]/coaches`

_Request Headers_
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`
_Sample Request Body_

```json
{
  "data": {
    "attributes": {
      "admin": "false",
      "email": "maddiebryan@example.com",
      "first_name": "Madeline",
      "last_name": "Bryan",
      "phone": "",
      "position_title": "Assistant to the Head Coach"
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
            "id": "1",
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
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/coaches \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"coaches","attributes":{"first_name":"Madeline","last_name":"Bryan", "email":"maddiebryan@example.com", "phone":"", "position_title": "Assistant to the Head Coach", "admin":"false"}, "relationships": {"organization": {"data":{"type":"organizations", "id":"1"}}, "team": {"data": [{"type":"teams", "id":"1"}]}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/coaches")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"coaches\",\"attributes\":{\"first_name\":\"Madeline\",\"last_name\":\"Bryan\",\"email\":\"maddiebryan@example.com\",\"phone\":\"\",\"position_title\":\"Assistant to the Head Coach\",\"admin\":\"false\"},\"relationships\":{\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"1\"}},\"team\":{\"data\":[{\"type\":\"teams\",\"id\":\"1\"}]}}}}"

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
/* 201 Created */
{
  "data": {
    "attributes": {
      "admin": true,
      "deleted": false,
      "email": "maddiebryan@example.com",
      "first-name": "Madeline",
      "last-name": "Bryan",
      "phone": "",
      "photo-url": "/images/default_user_image.png",
      "position-title": "Assistant to the Head Coach"
    },
    "id": "3",
    "links": {
      "self": "/api/team_edition/coaches/3"
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
            "id": "1",
            "type": "teams"
          }
        ]
      }
    },
    "type": "coaches"
  }
}
```

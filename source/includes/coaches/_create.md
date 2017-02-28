# CREATE A COACH

**POST `/api/team_edition/organizations/:organization_id/coaches`**

This endpoint creates a coach for an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Sample Request Body**

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

**Code Examples**

_cURL_

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/coaches \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --header 'content-type: application/vnd.api+json' \
  --data-binary '{"data":{"type":"coaches","attributes":{"first_name":"Madeline","last_name":"Bryan", "email":"maddiebryan@example.com", "phone":"", "position_title": "Assistant to the Head Coach", "admin":"false"}, "relationships": {"organization": {"data":{"type":"organizations", "id":"1"}}, "team": {"data": [{"type":"teams", "id":"1"}]}}}}' \
```


_Ruby Net::HTTP_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/coaches")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = "{\"data\":{\"type\":\"coaches\",\"attributes\":{\"first_name\":\"Madeline\",\"last_name\":\"Bryan\",\"email\":\"maddiebryan@example.com\",\"phone\":\"\",\"position_title\":\"Assistant to the Head Coach\",\"admin\":\"false\"},\"relationships\":{\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"1\"}},\"team\":{\"data\":[{\"type\":\"teams\",\"id\":\"1\"}]}}}}"

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

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

## Errors & Statuses

For errors, see relevant spec files.

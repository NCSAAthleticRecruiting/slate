# DELETE A COACH

**DELETE `/api/team_edition/coaches/:coach_id`**

This endpoint is responsible for deleting a coach.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request DELETE \
  --url http://qa.ncsasports.org/api/team_edition/coaches/7 \
  --header "session-token: eyJ0eXAiOiJKV1QiLCiJ9..." \
  --header 'content-type: application/vnd.api+json' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/coaches/7")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["content-type"] = 'application/vdb.json-api'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
/* 200 OK */
{
  "data": {
    "id": "7",
    "type": "coaches",
    "attributes": {
      "first-name": "Jon",
      "last-name": "Stewart",
      "email": "cjo.ncsa@gmail.com",
      "phone": "5558885858",
      "position-title": "Admin",
      "photo-url": "/images/default_user_image.png",
      "admin": true,
      "primary-contact": true,
      "deleted": true
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "4",
          "type": "organizations"
        }
      },
      "teams": {
        "data": []
      }
    },
    "links": {
      "self": "/api/team_edition/coaches/7"
    }
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files.

# GET A SPECIFIC TEAM

**GET `/api/team_edition/teams/:team_id`**


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
  "http://qa.ncsasports.org/api/team_edition/teams/2" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```

<br>

_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/teams/2")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


### Sample Response

```json
{
  "data": {
    "id": "2",
    "type": "teams",
    "attributes": {
      "name": "16 Elite",
      "sport": "Men's Volleyball",
      "sport-id": 17695,
      "active": true,
      "deleted": false
    },
    "relationships": {
      "organization-sport": {
        "data": {
          "id": "2",
          "type": "organization-sports"
        }
      }
    },
    "links": {
      "self": "/api/team_edition/teams/2"
    }
  },
  "links": {
    "self": "http://localhost:3000/api/team_edition/teams/2"
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

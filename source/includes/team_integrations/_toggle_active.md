# DEACTIVATE/ACTIVATE A TEAM

**PATCH `/api/team_edition/teams/12/toggle_active`**

This endpoint toggles a team's `active` field value in the database, setting it to either `true` or `false`.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/teams/6/toggle_active \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/teams/6/toggle_active")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "6",
    "type": "teams",
    "attributes": {
      "name": "Bill's Buddies",
      "sport": "Men's Lacrosse",
      "sport-id": 17707,
      "active": false,
      "deleted": false
    },
    "relationships": {
      "organization-sport": {
        "data": {
          "id": "4",
          "type": "organization-sports"
        }
      }
    },
    "links": {
      "self": "/api/team_edition/teams/6"
    }
  },
  "links": {
    "self": "http://qa.ncsasports.org/api/team_edition/teams/6"
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

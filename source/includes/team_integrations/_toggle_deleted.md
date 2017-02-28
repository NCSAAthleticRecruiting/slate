# SOFT-DELETE A TEAM

**PATCH `/api/team_edition/teams/:team_id/toggle_deleted`**

This endpoint soft-deletes a team (sets the `deleted` field value to `true` on the team record). At present this endpoint cannot undo a soft-delete.

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
  --url http://qa.ncsasports.org/api/team_edition/teams/9/toggle_deleted \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/teams/9/toggle_deleted")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request['content-type'] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```



## Responses

**Sample Successful Response**

```json
/* 200 OK */
{
  "data": {
    "id": "9",
    "type": "teams",
    "attributes": {
      "name": "Murray's Men's Volleyball Team",
      "sport": "Men's Volleyball",
      "sport-id": 17695,
      "active": true,
      "deleted": true
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
      "self": "/api/team_edition/teams/9"
    }
  },
  "links": {
    "self": "http://localhost:3000/api/team_edition/teams/9"
  }
}
```

## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

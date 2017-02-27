# CREATE A TEAM

**POST `/api/team_edition/organizations/:organization_id/teams`**

This endpoint creates a team for an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Code Examples**

**cURL**

```shell
curl --request POST \
  "http://qa.ncsasports.org/api/team_edition/organizations/1/teams" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data '{"data":{"type":"teams","attributes":{"name":"cristins fun team"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"organization_sport":{"data":{"type":"organization_sports","id":"1"}}}}}'
```

**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"teams\",\"attributes\":{\"name\":\"cristins fun team\"},\"relationships\":{\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"1\"}},\"organization_sport\":{\"data\":{\"type\":\"organization_sports\",\"id\":\"1\"}}}}}"

response = http.request(request)
puts response.read_body
```


### Sample Response

```json
{
  "data": {
    "id": "5",
    "type": "teams",
    "attributes": {
      "name": "cristins fun team",
      "sport": "Women's Volleyball",
      "sport-id": 17696,
      "active": true,
      "deleted": false
    },
    "relationships": {
      "organization-sport": {
        "data": {
          "id": "1",
          "type": "organization-sports"
        }
      }
    },
    "links": {
      "self": "/api/team_edition/teams/5"
    }
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

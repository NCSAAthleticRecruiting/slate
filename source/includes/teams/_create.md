# CREATE A TEAM

**POST `/api/team_edition/organizations/:organization_id/teams`**

This endpoint creates a team for an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Sample Request Payload**

```json
{
  "data": {
    "type": "teams",
    "attributes": {
      "name": "Volleyballers"
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "organizations",
          "id": "1"
        }
      },
      "organization_sport": {
        "data": {
          "type": "organization_sports",
          "id": "1"
        }
      }
    }
  }
}
```


**Code Examples**

_cURL_

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/teams \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"teams","attributes":{"name":"Volleyballers"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"organization_sport":{"data":{"type":"organization_sports","id":"1"}}}}}' \
```


_Ruby Net::HTTP_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/teams")
options = {"data":{"type":"teams","attributes":{"name":"Volleyballers"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"organization_sport":{"data":{"type":"organization_sports","id":"1"}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json

/* Completed 201 */
{
  "data": {
    "id": "12",
    "type": "teams",
    "attributes": {
      "name": "Volleyballers",
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
      "self": "/api/team_edition/teams/12"
    }
  }
}
```


## Errrors/Statuses

See relevant spec files.

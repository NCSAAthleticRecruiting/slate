# UPDATE A COACH

**PATCH `/api/team_edition/coaches/:coach_id`**

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Required Data**

* `type` ('coaches')
* changed attributes
* relationships
  - `organization`
  - `team`

**Sample Request Payload**

```json
{
  "data": {
    "type": "coaches",
    "attributes": {
      "last_name": "Shellenbarger",
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "organizations",
          "id": "1"
        }
      },
      "team": {
        "data": [
          {
            "type": "teams",
            "id": "2"
          }
        ]
      }
    }
  }
}
```


**Code Examples**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/coaches/2 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"coaches","attributes":{"last_name":"Shellenbarger"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"team":{"data":[{"type":"teams","id":"2"}]}}}}' \
```


_Ruby Net::HTTP_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/coaches/2")
options = {"data":{"type":"coaches","attributes":{"last_name":"Shellenbarger"},"relationships":{"organization":{"data":{"type":"organizations","id":"1"}},"team":{"data":[{"type":"teams","id":"2"}]}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```

<br>
<br>


## Responses


**Sample Successful Response**

```json
{
  "data": {
    "id": "2",
    "type": "coaches",
    "attributes": {
      "first-name": "Mia",
      "last-name": "Shellenbarger",
      "email": "mia@example.com",
      "phone": "",
      "position-title": "Head Coach",
      "photo-url": "/images/default_user_image.png",
      "admin": true,
      "primary-contact": false,
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
            "id": "2",
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

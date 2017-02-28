# CREATE EVALUATION FOR AN ATHLETE

**POST `/api/team_edition/athletes/:athlete_id/evaluation`**

This endpoint is responsible for creating an athlete's team edition evaluation, including a description and rating.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Required Data**

* `attributes`
  - _either_ `rating` _or_ `description`
* `type` ('evaluation')
* `relationships`
  - `athlete`
  - `organization`


**Sample Request Payload**

```json
{
  "data": {
    "type": "evaluation",
    "attributes": {
      "rating": 6
    },
    "relationships": {
      "athlete": {
        "data": {
          "type": "athletes",
          "id": "5"
        }
      },
      "organization": {
        "data": {
          "type": "organizations",
          "id": "1"
        }
      }
    }
  }
}
```

**Code Examples**

<aside class="notice">The current user (a `Coach` or `PartnerAdmin` must have admin priveleges (`admin: true`) or they'll get an unauthorized error.</aside>

_cURL_

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/athletes/5/evaluation \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"evaluation","attributes":{"rating":6},"relationships":{"athlete":{"data":{"type":"athletes","id":"5"}},"organization":{"data":{"type":"organizations","id":"1"}}}}}'
```

<br>

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/5/evaluation")
options = {"data":{"type":"evaluation","attributes":{"rating":6},"relationships":{"athlete":{"data":{"type":"athletes","id":"5"}},"organization":{"data":{"type":"organizations","id":"1"}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```

<br>

## Responses

**Sample Successful Response**

```json
{
  "status": "success"
}
```



## Errors & Statuses

See the relevant spec files to flesh this section out.

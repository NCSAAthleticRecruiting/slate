# CREATE EVALUATION FOR AN ATHLETE

**POST `/api/team_edition/athletes/:athlete_id/evaluation`**

This endpoint is responsible for creating an athlete's team edition evaluation, including a description and rating.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

<br>

**Data Attributes**

| Attribute         | `Type`/_Value_/Description        | Required?     |
|:-----------------:|:----------------------------------|:--------------|
|`description`      | Free text                         | `false`       |
|`rating`           | `Integer` (0-6)                   | `false`       |


**Sample Request Data**

```json
{
  "data": {
    "rating": 4,
    "description": "Dillon is, in my opinion, the platonic form for an athlete.",
    "type": "evaluation",
    "attributes": {
      "description": "A description that is changing."
    },
    "relationships": {
      "athlete": {
        "data": {
          "type": "athletates",
          "id": "2"
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

<aside class="notice">The current user must have admin priveleges or they'll get an unauthorized error.</aside>

_cURL_

```json
curl request POST \
  --url "http://qa.ncsasports.org/api/team_edition/athletes/:athlete_id/evaluation" \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{"data":{"rating":4,"description": "Dillon is, in my opinion, the platonic form for an athlete.", "type":"evaluation","attributes":{"description":"A description that is changing."},"relationships":{"athlete":{"data":{"type":"athletates","id":"2"}},"organization":{"data":{"type":"organizations","id":"1"}}}}}'
```

<br>

_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/5/evaluation")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"evaluation\",\"attributes\":{\"rating\":4,\"description\":\"Dillon is, in my opinion, the platonic form for an athlete.\"},\"relationships\":{\"athlete\":{\"data\":{\"type\":\"athletes\",\"id\":\"5\"}},\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"1\"}}}}}"

response = http.request(request)
puts response.read_body
```

<br>

## Responses

<aside class="notice"><ul><li>The _SessionUser_ referred to in the code is a wrapper for a `Coach` or `PartnerAdmin`, which is reflected in the `session-type` attribute</li><li>Note that the response object's "self link" has been updated in the AthleteIntegrations controller.</li></ul></aside>

**Sample Successful Response**

```json
/* For a Coach */
{
  "data": {
    "id": "1",
    "type": "sessions",
    "attributes": {
      "session-type": "coach",
      "token": "eyJ0eXAiOiJKV1QiLCJhbGci"
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}

/* For a Partner Admin */
{
  "data": {
    "id": "1",
    "type": "sessions",
    "attributes": {
      "session-type": "partner_admin",
      "token": "eyJ0eXAiOiJKV1QiLCJhbGci"
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}

```



## Errors & Statuses

See the relevant spec files to flesh this section out.

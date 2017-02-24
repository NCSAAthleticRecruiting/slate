# Create evaluation

**POST `/api/team_edition/athletes/15/evaluation`**

This endpoint is responsible for creating an athlete's team edition evaluation, including a description and rating.

### Sample Request Headers

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJ...     | `true`    |
| _Content-Type_    | `application/vnd.api+json` | `true`    |

### Request Parameters

| Parameter      | Required? | Description  |
|:--------------:|:---------:|:------------:|
|`description`   | `false`   |              |
|`rating`        | `false`   |              |


### Sample Requests

<aside class="notice">The coach editing the rating must be an admin in order for the request to suceed.</aside>

**cURL**

```json
curl request POST \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{"data":{"type":"evaluation","attributes":{"description":"A description that is changing."},"relationships":{"athlete":{"data":{"type":"athletates","id":"2"}},"organization":{"data":{"type":"organizations","id":"1"}}}}}'
  --data '{"data":{"type":"evaluation","attributes":{"rating":4,"description": "Dillon is, in my opinion, the platonic form for an athlete."},"relationships":{"athlete":{"data":{"type":"athletes","id":"5"}},"organization":{"data":{"type":"organizations","id":"1"}}}}}'
```

**Ruby Net::HTTP**

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

### Sample Response Body

<aside class="notice"><ul><li>The _SessionUser_ referred to in the code is a wrapper for a `Coach` or `PartnerAdmin`, which is reflected in the `session-type` attribute</li><li>Note that the response object's "self link" has been updated in the AthleteIntegrations controller.</li></ul></aside>

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

### Miscellaneous

**Help with JSON API Requests**

* <a href="http://jsonapi.org/format/#crud-creating">Creating a RESOURCE</a>
* <a href="http://jsonapi.org/format/#crud-updating">Updating a RESOURCE</a>
* <a href="http://jsonapi.org/format/#crud-updating-relationships">Updating RESOURCE Relationships</a>
* <a href="http://jsonapi.org/format/#crud-deleting">Deleting a RESOURCE</a>


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The resource requested is hidden for administrators only
404 | Not Found -- The specified resource could not be found
405 | Method Not Allowed -- You tried to access a resource with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The resource requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many resources! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.

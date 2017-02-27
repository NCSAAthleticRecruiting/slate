# CREATE RECOMMENDATION FOR ATHLETE

**POST `/api/team_edition/athletes/:athlete_id/recommendation`**

This endpoint creates a college recommendation from a coach.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request POST \
  "http://qa.ncsasports.org/api/team_edition/athletes/110/recommendation" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"recommendations","attributes":{"college_id":"15077","action":"create"},"relationships":{"athlete":{"data":{"type":"athletes","id":"110"}},"organization":{"data":{"type":"organizations","id":"15"}}}}}'
```

<br>

_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/110/recommendation")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"recommendations\",\"attributes\":{\"college_id\":\"15077\",\"action\":\"create\"},\"relationships\":{\"athlete\":{\"data\":{\"type\":\"athletes\",\"id\":\"110\"}},\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"15\"}}}}}"

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
{
  "details":"Recommendation created"
}
```

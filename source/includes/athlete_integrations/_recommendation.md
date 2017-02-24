# Create Athlete Recommendation

`POST /api/team_edition/athletes/:athlete_id/recommendation`

This endpoint creates a college recommendation from a coach.

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |

| Parameter    | Required? | Description         |
|:------------:|:---------:|:-------------------:|
| `athlete_id` | `true`    | query string param  |




### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Request Parameters

| Parameter   | Required? | Description         |
|:-----------:|:---------:|:-------------------:|
| `client_id` | `true`    | query string param  |


### Request Examples

**cURL**

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/athletes/110/recommendation \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"recommendations","attributes":{"college_id":"15077","action":"create"},"relationships":{"athlete":{"data":{"type":"athletes","id":"110"}},"organization":{"data":{"type":"organizations","id":"15"}}}}}'
```

<br>

**Ruby Net::HTTP**

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


### Sample Response

```json
{
  "details":"Recommendation created"
}
```

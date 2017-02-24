# Update athlete access and features for NCSA

**PUT `/api/team_edition/athletes/:client_id/grant_access_and_features`**

Handles the granting of additional access and features to NCSA applications for a single TED athlete.

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
curl --request PUT \
  --url http://qa.ncsasports.org/api/team_edition/athletes/53725/grant_access_and_features \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/53725/grant_access_and_features")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::PUT.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request['content-type'] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

### Sample Response

<aside class="notice">If the athlete is already enrolled in a paid membership with NCSA, then they will automatically get upgraded to an MVP membership now that they are also a TED membership.</aside>

```json
{
  "status":"success"
}
```

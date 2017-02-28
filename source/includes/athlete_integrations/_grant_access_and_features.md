# UPDATE ATHLETE NCSA MEMBERSHIP ACCESS & FEATURES

**PUT `/api/team_edition/athletes/:client_id/grant_access_and_features`**

Handles the granting of additional access and features to NCSA applications for a single TED athlete.


## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request PUT \
  --url http://qa.ncsasports.org/api/team_edition/athletes/53725/grant_access_and_features \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJ...' \
```

<br>

_Ruby Net::HTTP_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/53725/grant_access_and_features")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request['content-type'] = 'application/vnd.api+json'
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJ...'

response = http.request(request)
puts response.read_body
```


## Responses

<aside class="notice">If the athlete is already enrolled in a paid membership with NCSA, then they will automatically get upgraded to an MVP membership now that they are also a TED membership.</aside>

**Sample Successful Response**

```json
{
  "status":"success"
}
```


## Errors & Statuses

**404**

Meaning: athlete with the id provided could not be found. double check that you have the right athlete.

```json
{
  "details": "No athlete found"
}
```

* For more errors and statuses, see relevant spec files to flesh out this section.

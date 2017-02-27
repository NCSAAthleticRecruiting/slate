# UPDATE A TEAM

**PATCH `/api/team_edition/teams/:team_id`**

This endpoint updates a single team.


## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Samples**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/teams/5 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data-binary '{"data":{"id":"5","type":"teams","attributes":{"name":"the best team"}}}'
```

__Ruby Net::Http__

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/teams/5/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"id\":\"5\",\"type\":\"teams\",\"attributes\":{\"name\":\"the best team\"}}}"

response = http.request(request)
puts response.read_body
```


## Responses


**Sample Successful Response**

`Status: 204 No Content`



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

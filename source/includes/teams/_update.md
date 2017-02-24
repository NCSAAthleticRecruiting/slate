# Update a team

**PATCH `/api/team_edition/teams/:team_id`**

This endpoint updates a single team.

### Sample Request Headers

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Requests

**cURL**

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/teams/5 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data-binary '{"data":{"id":"5","type":"teams","attributes":{"name":"the best team"}}}'
```

**Ruby Net::Http**

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


### Sample Response

`204 No Content`

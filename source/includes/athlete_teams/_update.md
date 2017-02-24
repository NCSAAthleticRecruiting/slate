# Update an athlete's teams

**PATCH `/api/team_edition/athletes/:athlete_id/relationships/teams`**

This endpoint updates the information about teams that an athlete has played on or is currently playing on.


**Pretty Example of Request Payload**

<aside class="notice">The request payload will contain the data for each team the athlete is associated with, including whatever changes/updates that were just made.</aside>

```json
{
  "data": [
    {
      "type": "teams",
      "id": "2",
      "meta": {
        "active": true,
        "primary": true
      }
    },
    {
      "type": "teams",
      "id": "4",
      "meta": {
        "active": true,
        "primary": false
      }
    }
  ]
}
```



### Sample Requests

**cURL**

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data '{"data":[{"type":"teams","id":"2","meta":{"active":true,"primary":true}},{"type":"teams","id":"4","meta":{"active":true,"primary":false}}]}'
```

**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":[{\"type\":\"teams\",\"id\":\"2\",\"meta\":{\"active\":true,\"primary\":true}},{\"type\":\"teams\",\"id\":\"4\",\"meta\":{\"active\":true,\"primary\":false}}]}"

response = http.request(request)
puts response.read_body
```


### Sample Response

A successful response will have a `204 No Content` status code.


### Miscellaneous
* For errors, see: `/team_edition_service/spec/interactors/update_athlete_teams_spec.rb`

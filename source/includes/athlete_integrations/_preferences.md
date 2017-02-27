# SHOW PREFERENCES FOR ATHLETE

**GET `/api/team_edition/athletes/:athlete_id/preferences`**

This endpoint retrieves the athlete's preferences.


## Requests

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/5/preferences \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

<br>

_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/5/preferences")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>

## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "5",
    "type": "athlete-preferences",
    "attributes": {
      "athletic-selectivity": [],
      "academic-selectivity": [],
      "college-setting": [],
      "college-type": [],
      "major": [],
      "enrollment-min": null,
      "enrollment-max": null,
      "location": [],
      "id": 5
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/5/preferences"
  },
  "relationships": {
    "athlete": {
      "data": {
        "id": 5,
        "type": "athletes"
      }
    }
  }
}
```


# GET ALL TEAMS FOR ATHLETE

** GET `/api/team_edition/athletes/:athlete_id/relationships/teams`**

This endpoint gets the teams an athlete belongs to.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Samples**

_cURL_

```shell
curl --request GET \
  "http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```

<br>

**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```



## Responses

**Response Types**

| Status Code                    | Description/Cause                       |
|--------------------------------|-----------------------------------------|
| 200 OK                         | Successfully retrieved athlete's teams  |



**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "10",
      "type": "athlete-teams",
      "attributes": {
        "primary": true,
        "active": true
      },
      "relationships": {
        "athlete": {
          "data": {
            "id": "10",
            "type": "athletes"
          }
        },
        "team": {
          "data": {
            "id": "1",
            "type": "teams"
          }
        }
      }
    },
    {
      "id": "45",
      "type": "athlete-teams",
      "attributes": {
        "primary": false,
        "active": false
      },
      "relationships": {
        "athlete": {
          "data": {
            "id": "10",
            "type": "athletes"
          }
        },
        "team": {
          "data": {
            "id": "3",
            "type": "teams"
          }
        }
      }
    },
    {
      "id": "46",
      "type": "athlete-teams",
      "attributes": {
        "primary": false,
        "active": true
      },
      "relationships": {
        "athlete": {
          "data": {
            "id": "10",
            "type": "athletes"
          }
        },
        "team": {
          "data": {
            "id": "5",
            "type": "teams"
          }
        }
      }
    }
  ]
}
```

# Get an athlete's teams

** GET `/api/team_edition/athletes/:athlete_id/relationships/teams`**

This endpoint shows the teams that an athlete plays on

### Sample Requests

**cURL**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

<br>

**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/10/relationships/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```



### Sample Response

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

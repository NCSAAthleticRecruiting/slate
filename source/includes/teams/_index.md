# Show Teams

**GET `/api/team_edition/organizations/:organization_id/teams`**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/teams \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

<br>

**Ruby Net::Http**


```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


### Sample Response

**304 Not Modified**

```json
{
  "data": [
    {
      "id": "2",
      "type": "teams",
      "attributes": {
        "name": "16 Elite",
        "sport": "Men's Volleyball",
        "sport-id": 17695,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "2",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/2"
      }
    },
    {
      "id": "1",
      "type": "teams",
      "attributes": {
        "name": "18 Elite",
        "sport": "Women's Volleyball",
        "sport-id": 17696,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "1",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/1"
      }
    },
    {
      "id": "4",
      "type": "teams",
      "attributes": {
        "name": "Men's Traveling Elite",
        "sport": "Men's Volleyball",
        "sport-id": 17695,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "2",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/4"
      }
    },
    {
      "id": "3",
      "type": "teams",
      "attributes": {
        "name": "Women's Traveling Elite",
        "sport": "Women's Volleyball",
        "sport-id": 17696,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "1",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/3"
      }
    }
  ],
  "links": {
    "self": "http://qa.ncsasports.org/api/team_edition/organizations/1/teams"
  }
}
```

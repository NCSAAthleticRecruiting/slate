# GET ALL TEAMS FOR AN ORGANIZATION

**GET `/api/team_edition/organizations/:organization_id/teams`**

This endpoint is responsible for retrieving all the teams for a given organization.

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
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/teams \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/teams")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
/* 200 OK */
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
    "self": "http://localhost:3000/api/team_edition/organizations/1/teams"
  }
}

```



**Response Types**

| Status Code                    | Description/Cause                 |
|--------------------------------|-----------------------------------|
| 200 OK                         | Successfully retrieved teams      |
| 404 Not Found                  | organization_id doesn't exist     |


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

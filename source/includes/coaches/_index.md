# Show Coaches Index Page
<br>

## _Overview_

`GET /api/team_edition/organizations/[:organization_id]/coaches`

_Request Headers_
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/coaches \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/coaches")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": [
    {
      "id": "2",
      "type": "coaches",
      "attributes": {
        "first-name": "Mia",
        "last-name": "Hamm",
        "email": "mia@example.com",
        "phone": null,
        "position-title": "Head Coach",
        "photo-url": "/images/default_user_image.png",
        "admin": false,
        "deleted": false
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        },
        "teams": {
          "data": [
            {
              "id": "2",
              "type": "teams"
            }
          ]
        }
      },
      "links": {
        "self": "/api/team_edition/coaches/2"
      }
    },
    {
      "id": "1",
      "type": "coaches",
      "attributes": {
        "first-name": "Tim",
        "last-name": "Smith",
        "email": "tim@example.com",
        "phone": null,
        "position-title": "Head Coach",
        "photo-url": "/images/default_user_image.png",
        "admin": false,
        "deleted": false
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        },
        "teams": {
          "data": [
            {
              "id": "1",
              "type": "teams"
            }
          ]
        }
      },
      "links": {
        "self": "/api/team_edition/coaches/1"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/coaches"
  }
}
```

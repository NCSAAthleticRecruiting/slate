# GET ALL COACHES FOR ORGANIZATION

**GET `/api/team_edition/organizations/:organization_id/coaches`**

This endpoint retrieves all of the coaches belonging to an organization.

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
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/coaches \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/coaches")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Response Types**

| Status Code                    | Description/Cause                 |
|--------------------------------|-----------------------------------|
| 200 OK                         | Successfully retrieved coaches    |


**Sample Successful Response**

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
        "primary-contact": false,
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
        "admin": true,
        "primary-contact": false,
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

## Errors & Statuses

* For errors, see relevant spec files.

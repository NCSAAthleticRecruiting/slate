# GET ALL PARTNER ADMINS FOR PARTNER

**GET `/api/team_edition/partners/1/partner_admins`**

This endpoint is responsible for retrieving all partner admins.

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
  "http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Response Types**

| Status Code                    | Description/Cause                          |
|--------------------------------|--------------------------------------------|
| 200 OK                         | Successfully retrieved partner admins      |
| 404 Not Found                  | partner_id doesn't exist                   |

```json
{
  "data": [
    {
      "id": "1",
      "type": "partner-admins",
      "attributes": {
        "first-name": "John",
        "last-name": "Smith",
        "email": "john@example.com"
      },
      "relationships": {
        "partner": {
          "data": {
            "id": "1",
            "type": "partners"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "partner-admins",
      "attributes": {
        "first-name": "Bill",
        "last-name": "Murray",
        "email": "thisisnt@billmurraysemail.com"
      },
      "relationships": {
        "partner": {
          "data": {
            "id": "1",
            "type": "partners"
          }
        }
      }
    }
  ]
}
```


## Errrors/Statuses

See relevant spec files.

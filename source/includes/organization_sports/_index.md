# Show all sports (for an organization)

**GET `/api/team_edition/organizations/:organization_id/organization_sports`**

This endpoint is responsible for showing the sports that an organization has.

### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Requests

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/organization_sports \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/organization_sports")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request['content-type'] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```



### Sample Response

```json
{
  "data": [
    {
      "id": "1",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Women's Volleyball",
        "sport-id": 17696
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organizations/1/organization_sports"
      }
    },
    {
      "id": "2",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Men's Volleyball",
        "sport-id": 17695
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organizations/2/organization_sports"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/organization_sports"
  }
}
```

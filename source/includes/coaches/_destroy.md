# Show All Colleges

**DELETE `/api/team_edition/coaches/:coach_id`**

This endpoint is responsible for deleting a coach.

### Sample Request Headers

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Request Examples

**cURL**

```shell
curl --request DELETE \
  --url http://qa.ncsasports.org/api/team_edition/coaches/3
  --header "session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
  --header "content-type: application/vnd.api+json"
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://localhost:3000/api/team_edition/coaches/3")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Delete.new(url)
request["content-type"] = 'application/vdb.json-api'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'

response = http.request(request)
puts response.read_body
```

### Sample Response

```json
{
  "data": {
    "id": "3",
    "type": "coaches",
    "attributes": {
      "first-name": "Delete me",
      "last-name": "as a test",
      "email": "test@justanexample.com",
      "phone": "",
      "position-title": "deleteable coach",
      "photo-url": "/images/default_user_image.png",
      "admin": false,
      "deleted": true
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
      "self": "/api/team_edition/coaches/3"
    }
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files.

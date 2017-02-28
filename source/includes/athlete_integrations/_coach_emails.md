# GET ATHLETE'S COACH EMAIL DATA

**GET `/api/team_edition/athletes/:client_id/coach_emails`**

This endpoint retrieves information about coaches the athlete has received messages from.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/573275/coach_emails \
  --header "content-type: application/vnd.api+json" \
  --header "session-token: eyJ0eXAiOiJKV1QiLCiJ9..." \
```


_Ruby Net:Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/573275/coach_emails")

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
  "data": {
    "type": "team_edition_coach",
    "attributes": [
      {
        "first_name": "Tim",
        "last_name": "Smith",
        "email": "tim@example.com",
        "org_name": "Spree Volleyball"
      }
    ]
  }
}
```


## Errors & Statuses

See the relevant spec files to flesh this section out.

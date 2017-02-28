# GET A SINGLE PARTNER

**GET `/api/team_edition/partners/:partner_id`**

This endpoint retrieves the partner with the partner_id in the url.

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
  --url http://qa.ncsasports.org/api/team_edition/partners/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1")

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
{
  "data": {
    "id": "1",
    "type": "partners",
    "attributes": {
      "name": "Next College Student Athlete",
      "email": "TeamEdition@ncsasports.org"
    },
    "links": {
      "self": "/api/team_edition/partners/1"
    }
  },
  "links": {
    "self": "/api/team_edition/partners/1"
  }
}
```

## Errrors/Statuses

See relevant spec files.

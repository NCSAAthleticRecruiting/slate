# RESPOND/PING

**GET `/api/team_edition/ping`**

Health Check for Team Edition application.

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
  --url http://qa.ncsasports.org/api/team_edition/ping /
  --header 'content-type: application/vnd.api+json' /
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' /
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/ping")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
/* 200 OK */
pong
```


## Errors & Statuses

For errors, see relevant spec files to flesh out this section.

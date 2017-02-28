# DESTROY A SESSION

**GET `/api/team_edition/sign_out`**

This endpoint terminates a session.

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
  --url http://qa.ncsasports.org/api/team_edition/sign_out \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/sign_out")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request['content-type'] = 'application/vnd.api+json'
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

`Status: 204 No Content`


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

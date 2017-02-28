# UPDATE A PASSWORD FOR A USER

**PATCH `/api/team_edition/password_resets'`**

This endpoint will update a user's password after their first login.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Sample Request Payload**

```json
{
  "data": {
    "type": "password_resets",
    "attributes": {
      "password": "password"
    }
  }
}
 ```


**Code Samples**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/password_resets \
  --header 'content-type: application/vnd.api+json' \
  --data-binary '{"data":{"type":"password_resets","attributes":{"password":"password"}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/password_resets")
options = {"data":{"type":"password_resets","attributes":{"password":"password"}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "2",
    "type": "sessions",
    "attributes": {
      "session-type": "coach",
      "token": "eyJ0eXAiOiJKV1QiLCiJ9..."
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}
```

## Errrors/Statuses

See relevant spec files.

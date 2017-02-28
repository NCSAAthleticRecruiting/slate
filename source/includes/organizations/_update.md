# UPDATE AN ORGANIZATION

**PATCH `/api/team_edition/organizations/:organization_id`**

This endpoint is responsible for updating an existing organziation.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Sample Request Payload**

```json
/* for updating "name"*/
{
  "data": {
    "type": "organizations",
    "id": "3",
    "attributes": {
      "name": "Other Sports with Bill Murray"
    }
  }
}
```

**Code Examples**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/organizations/3 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"organizations","id":"3","attributes":{"name":"Murrays Volleyball Club"}}}' \
```


_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1")
options = {"data":{"type":"organizations","id":"3","attributes":{"name":"Murrays Volleyball Club"}}}
http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Response

**Sample Success Response**

`Status: 204 No Content`


## Errrors/Statuses

See relevant spec files.

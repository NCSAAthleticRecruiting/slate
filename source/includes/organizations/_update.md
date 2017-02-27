# UPDATE AN ORGANIZATION

**PATCH `/api/team_edition/organizations/3`**

This endpoint is responsible for updating an existing organziation.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


<!-- **Data Attributes**

| Parameter           | `Type`      | Required?     | Description           |
|:------------------- |:------------|:--------------|:----------------------|
| `email`             | String      | `true`        |                       |
| `password`          | String      | `true`        |                       |
| `attributes`        | Hash        | `true`        |                       |
| `attribute["name"]` | String      | `false`       | organization's name   |

 -->
<!-- **Organization Attributes**


```ruby
    :name,
    :zip_code,
    :address,
    :city,
    :state,
    :email,
    :phone,
    :website
  ```
 -->
**Sample Request Payload**

<aside class="notice>Must meet the JSON Api spec requirements for <a href="http://jsonapi.org/format/#crud-updating">updating a resource</a></aside>


```json
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


**Code Examples (for updating "name")**

_cURL_

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{"data":{"type":"organizations","id":"1","attributes":{"name":"Spree Volleyball Club"}}}'
```


_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request.body = "{\"data\":{\"type\":\"organizations\",\"id\":\"1\",\"attributes\":{\"name\":\"Spree Volleyball Club\"}}}"

response = http.request(request)
puts response.read_body
```


## Response

**Sample Success Response**


`Status Code: 204 No Content`


## Errrors/Statuses

See relevant spec files.

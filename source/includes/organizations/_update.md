# Update an organization

**PATCH `/api/team_edition/organizations/3`**

This endpoint is responsible for updating an existing organziation.

## Request

**Headers**

| Header            | Value                         | Required?  |
|:------------------|:------------------------------|:-----------|
| _Content-Type_    | application/vnd.api+json      | `true`     |

<br>

**Data Attributes**

| Parameter           | `Type`      | Required?     | Description           |
|:------------------- |:------------|:--------------|:----------------------|
| `email`             | String      | `true`        |                       |
| `password`          | String      | `true`        |                       |
| `attributes`        | Hash        | `true`        |                       |
| `attribute["name"]` | String      | `false`       | organization's name   |


**Organization Attributes**


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

``
#### 1. cURL (for updating `organization.name`)

```shell
curl --request PATCH \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{"data":{"type":"organizations","id":"1","attributes":{"name":"Spree Volleyball Club"}}}'
```


#### 2. Ruby Net::HTTP (for updating `organization.name`)

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

<br>
<br>

## Response

**Sample Success Response**


`Status Code: 204 No Content`

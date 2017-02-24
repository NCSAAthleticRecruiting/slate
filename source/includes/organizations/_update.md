# Update Organization
<br>

## _Overview_

* `PATCH /api/team_edition/organizations/[:organization_id]`

* Request Headers
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`
  * Sample Request Body (for updating `organization.name`)
    ```json
      {
        "data": {
          "type": "organizations",
          "id":"1",
          "attributes": {
            "name":"Spree Volleyball Club"
          }
        }
      }
    ```


<br>
## _Sample Successful Requests_

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

## _Sample Successful Response_

* `Response`: `HTTP/1.1 204 No Content`

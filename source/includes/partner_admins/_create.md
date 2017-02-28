# CREATE A PARTNER ADMIN

**POST `/api/team_edition/partners/:partner_id/partner_admins`**

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Required Data**

* `attributes`
  - `first_name`
  - `last_name`
  - `email`
* `id`
* `type` ('partner_admins')
* `relationships['partner']`

**Sample Request Body**

```json
{
  "data": {
    "id": "2",
    "type": "partner-admins",
    "attributes": {
      "first-name": "Justice",
      "last-name": "Johnson",
      "email": "justjo@example.com"
    },
    "relationships": {
      "partner": {
        "data": {
          "id": "1",
          "type": "partners"
        }
      }
    }
  }
}
```


**Code Examples**

_cURL_

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data-binary '{"data":{"type":"partner_admins","attributes":{"first_name":"Justice","last_name":"Johnson","email":"justjo@example.com"},"relationships":{"partner":{"data":{"type":"partners"}}}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = "{\"data\":{\"type\":\"partner_admins\",\"attributes\":{\"first_name\":\"Justice\",\"last_name\":\"Johnson\",\"email\":\"justjo@example.com\"},\"relationships\":{\"partner\":{\"data\":{\"type\":\"partners\"}}}}}"

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "3",
    "type": "partner-admins",
    "attributes": {
      "first-name": "Justice",
      "last-name": "Johnson",
      "email": "justjo@example.com"
    },
    "relationships": {
      "partner": {
        "data": {
          "id": "1",
          "type": "partners"
        }
      }
    }
  }
}
```



## Errrors/Statuses

See relevant spec files.

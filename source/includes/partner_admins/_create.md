# Create PartnerAdmin
<br>

## _Overview_

* `POST /api/team_edition/partners/[:partner_id]/partner_admins`

**Request Headers**
* `Content-Type`: `application/vnd.api+json`
* `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

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


<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"partner_admins","attributes":{"first_name":"Justice","last_name":"Johnson","email":"justjo@example.com"},"relationships":{"partner":{"data":{"type":"partners"}}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"partner_admins\",\"attributes\":{\"first_name\":\"Justice\",\"last_name\":\"Johnson\",\"email\":\"justjo@example.com\"},\"relationships\":{\"partner\":{\"data\":{\"type\":\"partners\"}}}}}"

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

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


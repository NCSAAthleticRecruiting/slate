# Index Page for Partner Admins
<br>

## _Overview_

`GET /api/team_edition/partners/1/partner_admins`

_Request Headers_
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/partner_admins")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": [
    {
      "id": "1",
      "type": "partner-admins",
      "attributes": {
        "first-name": "John",
        "last-name": "Smith",
        "email": "john@example.com"
      },
      "relationships": {
        "partner": {
          "data": {
            "id": "1",
            "type": "partners"
          }
        }
      }
    },
    {
      "id": "2",
      "type": "partner-admins",
      "attributes": {
        "first-name": "Cristin",
        "last-name": "O'Connor",
        "email": "coconnor@ncsasports.org"
      },
      "relationships": {
        "partner": {
          "data": {
            "id": "1",
            "type": "partners"
          }
        }
      }
    },
    {
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
  ]
}
```






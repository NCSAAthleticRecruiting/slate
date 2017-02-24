# Create Organization
<br>

## _Overview_

`POST /api/team_edition/partners/[:partner_id]/organizations`

_Request Headers_
* `Content-Type`: `application/vnd.api+json`
* `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

_Sample Request Body_

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "Lincoln Park Women's Soccer",
      "address": "1333 N. Kingsbury Street",
      "email": "cristin@example.com",
      "phone": "5036805403",
      "city": "Chicago",
      "state": "IL",
      "zip_code": "60642",
      "website": "http://fakesoccerclub.com"
    },
    "relationships": {
      "partner": {
        "data": {
          "type": "partners"
        }
      },
      "sport": {
        "data": [
          {
            "type": "sports",
            "id": "17684"
          }
        ]
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
  --url http://qa.ncsasports.org/api/team_edition/partners/1/organizations \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"organizations","attributes":{"name":"Lincoln Park Womens Soccer","address":"1333 N. Kingsbury Street","email":"cristin@example.com","phone":"5036805403","city":"Chicago","state":"IL","zip_code":"60642","website":"http://fakesoccerclub.com"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17684"}]}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"organizations\",\"attributes\":{\"name\":\"Lincoln Park Womens Soccer\",\"address\":\"1333 N. Kingsbury Street\",\"email\":\"cristin@example.com\",\"phone\":\"5036805403\",\"city\":\"Chicago\",\"state\":\"IL\",\"zip_code\":\"60642\",\"website\":\"http://fakesoccerclub.com\"},\"relationships\":{\"partner\":{\"data\":{\"type\":\"partners\"}},\"sport\":{\"data\":[{\"type\":\"sports\",\"id\":\"17684\"}]}}}}"

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": {
    "id": "2",
    "type": "organizations",
    "attributes": {
      "name": "Lincoln Park Women's Soccer",
      "zip-code": "60642",
      "address": "1333 N. Kingsbury Street",
      "city": "Chicago",
      "state": "IL",
      "email": "cristin@example.com",
      "phone": "5036805403",
      "website": "http://fakesoccerclub.com",
      "logo-url": "/images/default_organization_image.png",
      "current-contract-ids": [],
      "sports": [
        "Women's Soccer"
      ],
      "primary-contact-name": null
    },
    "links": {
      "self": "/api/team_edition/organizations/2"
    }
  }
}
```

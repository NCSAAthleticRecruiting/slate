# Create an organization

<br>

**POST `/api/team_edition/partners/[:partner_id]/organizations`**

This endpoint creates an organization (which belogns to a partner).

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJ...     | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


`name`
`zip_code`
`primary_contact_first_name`

**Sample Request Payload**

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "Sports for Teenz",
      "address": "",
      "email": "lukejohnson@fakeperson.com",
      "phone": "555-503-5045",
      "city": "",
      "state": "",
      "zip_code": "66505",
      "website": "",
      "first_name": "Luke",
      "last_name": "Johnson"
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
            "id": "17707"
          }
        ]
      }
    }
  }
}
```

_Sample Request Body_

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "Volleyball with Bill Murray",
      "address": "1333 North Kingsbury Street",
      "email": "cjo.ncsa+test@gmail.com",
      "phone": "5036805403",
      "city": "Chicago",
      "state": "IL",
      "zip_code": "60642",
      "website": "",
      "first_name": "Cristin",
      "last_name": "O'Connor"
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
            "id": "17696"
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




new:


  curl 'http://localhost:3000/api/team_edition/partners/1/organizations' -H 'Origin: http://localhost:8080' -H 'Accept-Encoding: gzip, deflate, br' -H 'Accept-Language: en-US,en;q=0.8,es-MX;q=0.6,es;q=0.4' -H 'User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Safari/537.36' -H 'content-type: application/vnd.api+json' -H 'Accept: */*' -H 'Referer: http://localhost:8080/' -H 'Connection: keep-alive' -H 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpZCI6MSwidHlwZSI6InBhcnRuZXJfYWRtaW4iLCJwaHJhc2UiOiIkMmEkMTAkUVA3SjRLdjJCWDZQNTZzTXFZR0p4ZVcuMlpNYjUzVzhKcW0yQ3ovTS9udTVTWk1TaUhsRkMiLCJ1c2VyX2ZpcnN0X25hbWUiOiJKb2huIiwidXNlcl9sYXN0X25hbWUiOiJTbWl0aCIsInBhcnRuZXJfaWQiOjEsImV2ZW50X2lkIjoxMjM0NSwiZXhwIjoxNDkwNDAxMzM3fQ.-xHRHwKVH-Mavt7r_-k5yg15HDqxNftSgi_xzqgAXwg' --data-binary $'{"data":{"type":"organizations","attributes":{"name":"Bill Murray","address":"1333 Nor","email":"cjo.ncsa+test@gmail.com","phone":"5036805403","city":"Chicago","state":"IL","zip_code":"60642","website":"","first_name":"Cristin","last_name":"O\'Connor"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17696"}]}}}}' --compressed

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

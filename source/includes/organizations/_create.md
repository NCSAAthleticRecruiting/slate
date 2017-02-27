# CREATE AN ORGANIZATION FOR A PARTNER

**POST `/api/team_edition/partners/[:partner_id]/organizations`**

This endpoint creates an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Required Attributes**

<!-- * `partner_id` (url parameter)
* `name`
* `zip_code`
* `primary_contact_first_name` -->

**Sample Request Payload**

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "Volleyball with Bill Murray",
      "address": "1333 North Kingsbury Street",
      "email": "lukejohnson@fakeperson.com",
      "phone": "5036805555",
      "city": "Chicago",
      "state": "IL",
      "zip_code": "60642",
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
            "id": "17696"
          }
        ]
      }
    }
  }
}
```


**Code Examples**

_cURL_

```shell
curl --request POST \
  "http://qa.ncsasports.org/api/team_edition/partners/1/organizations" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"organizations","attributes":{"name":"Lincoln Park Womens Soccer","address":"1333 N. Kingsbury Street","email":"cristin@example.com","phone":"5036805403","city":"Chicago","state":"IL","zip_code":"60642","website":"http://fakesoccerclub.com"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17684"}]}}}}'
  --data-binary '{"data":{"type":"organizations","attributes":{"name":"Volleyball with Bill Murray","address":"1333 North Kingsbury Street","email":"lukejohnson@fakeperson.com","phone":"5036805555","city":"Chicago","state":"IL","zip_code":"60642","website":"","first_name":"Luke","last_name":"Johnson"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17696"}]}}}}'

```


_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations")
options = {"data":{"type":"organizations","attributes":{"name":"Volleyball with Bill Murray","address":"1333 North Kingsbury Street","email":"lukejohnson@fakeperson.com","phone":"5036805555","city":"Chicago","state":"IL","zip_code":"60642","website":"","first_name":"Luke","last_name":"Johnson"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17696"}]}}}}
http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```

<br>
<br>

## Responses

**Sample Successful Response**

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


## Errrors/Statuses

See relevant spec files.

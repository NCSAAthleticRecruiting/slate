# GET ALL ORGANIZATIONS FOR PARTNER

**GET `/api/team_edition/partners/:partner_id/organizations`**

This endpoint retrieves all of the organizations for a specific partner.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Code Samples**

_cURL_

```shell
curl -X GET \
  "http://qa.ncsasports.org/api/team_edition/partners/1/organizations" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```

_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```




## Responses

**Response Types**

| Status Code                    | Description/Cause                 |
|--------------------------------|-----------------------------------|
| 201 OK                         | Successfully retrieved teams      |
| 404 Not Found                  | organization_id doesn't exist     |



**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "1",
      "type": "organizations",
      "attributes": {
        "name": "Spree Volleyball",
        "zip-code": "56906",
        "address": "234 Maple Lane",
        "city": "Chicago",
        "state": "IL",
        "email": "org@example.com",
        "phone": "3122234567",
        "website": "http://www.example.com",
        "logo-url": "/images/default_organization_image.png",
        "current-contract-ids": [],
        "sports": [
          "Women's Volleyball",
          "Men's Volleyball"
        ],
        "primary-contact-name": null
      },
      "links": {
        "self": "/api/team_edition/organizations/1"
      }
    },
    {
      "id": "2",
      "type": "organizations",
      "attributes": {
        "name": "Bill Murray",
        "zip-code": "60642",
        "address": "1333 Nor",
        "city": "Chicago",
        "state": "IL",
        "email": "cjo.ncsa+test@gmail.com",
        "phone": "5036805403",
        "website": "",
        "logo-url": "/images/default_organization_image.png",
        "current-contract-ids": [],
        "sports": [
          "Women's Volleyball"
        ],
        "primary-contact-name": "Cristin O'Connor"
      },
      "links": {
        "self": "/api/team_edition/organizations/2"
      }
    },
    {
      "id": "3",
      "type": "organizations",
      "attributes": {
        "name": "Other Sports with Bill Murray",
        "zip-code": "66505",
        "address": "",
        "city": "",
        "state": "",
        "email": "lukejohnson@fakeperson.com",
        "phone": "555-503-5045",
        "website": "",
        "logo-url": "/images/default_organization_image.png",
        "current-contract-ids": [],
        "sports": [
          "Men's Lacrosse"
        ],
        "primary-contact-name": "Luke Johnson"
      },
      "links": {
        "self": "/api/team_edition/organizations/3"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/partners/1/organizations"
  }
}
```

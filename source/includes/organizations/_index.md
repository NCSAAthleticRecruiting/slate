# Show all organizations (by partner)

**GET `/api/team_edition/partners/[:partner_id]/organizations`**

This endpoint retrieves all of the organizations for a specific partner.

### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Request Examples

**cURL**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/partners/1/organizations/
  --header "session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
  --header "content-type: application/vnd.api+json"
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```




### Sample Response

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
        "current-contract-ids": [
          1
        ],
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
        "name": "Redwood Volleyball",
        "zip-code": "56907",
        "address": "3320 Wight Lane",
        "city": "Chicago",
        "state": "IL",
        "email": "org@example.com",
        "phone": "3122234567",
        "website": "http://www.example.com",
        "logo-url": "/images/default_organization_image.png",
        "current-contract-ids": [
          2
        ],
        "sports": [
          "Women's Volleyball"
        ],
        "primary-contact-name": null
      },
      "links": {
        "self": "/api/team_edition/organizations/2"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/partners/1/organizations"
  }
}
```

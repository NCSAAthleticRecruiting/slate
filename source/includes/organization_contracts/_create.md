# Create OrganizationContract
<br>

## _Overview_

* `POST /api/team_edition/organizations/[:organization_id]/organization_contracts`

**Request Headers**
* `Content-Type`: `application/vnd.api+json`
* `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

**Sample Request Body**

```json
{
  "data": {
    "attributes": {
      "current-contract-amount": "2160.0",
      "end-date": "2018-02-20",
      "modifier": "1.0",
      "number-of-athletes": 0,
      "number-of-payments": 1,
      "number-of-teams": 1,
      "sport-name": "Soccer",
      "start-date": "2017-02-20"
    },
    "id": "1",
    "links": {
      "self": "/api/team_edition/organization_contracts/1"
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "2",
          "type": "organizations"
        }
      },
      "sport": {
        "data": {
          "id": "3",
          "type": "sports"
        }
      }
    },
    "type": "organization-contracts"
  },
  "links": {
    "self": "/api/team_edition/organization_contracts/1"
  }
}
```


<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"organization_contracts","attributes":{"start_date":"2017-02-20","first_payment_date":"2017-02-20","number_of_payments":1,"number_of_teams":"1","modifier":1,"amount":2160},"relationships":{"organization":{"data":{"type":"organizations","id":"2"}},"sport":{"data":{"type":"sports","id":"3"}}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"organization_contracts\",\"attributes\":{\"start_date\":\"2017-02-20\",\"first_payment_date\":\"2017-02-20\",\"number_of_payments\":1,\"number_of_teams\":\"1\",\"modifier\":1,\"amount\":2160},\"relationships\":{\"organization\":{\"data\":{\"type\":\"organizations\",\"id\":\"2\"}},\"sport\":{\"data\":{\"type\":\"sports\",\"id\":\"3\"}}}}}"

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
      "email": "cristinoconnor@me.com",
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

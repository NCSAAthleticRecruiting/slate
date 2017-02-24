# Index Page for Organization Contracts
<br>

## _Overview_

* `GET /api/team_edition/organizations/[:organization_id]/organization_contracts`
* Request Headers
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts")

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
      "type": "organization-contracts",
      "attributes": {
        "start-date": "2017-02-20",
        "end-date": "2018-02-20",
        "modifier": "1.0",
        "number-of-payments": 1,
        "number-of-teams": 1,
        "number-of-athletes": 0,
        "current-contract-amount": "2160.0",
        "sport-name": "Soccer"
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
      "links": {
        "self": "/api/team_edition/organization_contracts/1"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/2/organization_contracts"
  }
}
```

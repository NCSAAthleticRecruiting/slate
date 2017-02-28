# GET AN ORGANIZATION'S CONTRACT

**GET `/api/team_edition/organizations/1/organization_contracts`**

This endpoint retrieves the contract for an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/organization_contracts \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --header 'content-type: application/vnd.api+json' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/organization_contracts")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Responsse**

```json
{
  "data": [
    {
      "id": "1",
      "type": "organization-contracts",
      "attributes": {
        "start-date": "2017-02-21",
        "end-date": "2018-02-21",
        "modifier": "1.0",
        "number-of-payments": 1,
        "number-of-teams": 4,
        "number-of-athletes": 44,
        "current-contract-amount": "6240.0",
        "sport-name": "Volleyball"
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        },
        "sport": {
          "data": {
            "id": "2",
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
    "self": "/api/team_edition/organizations/1/organization_contracts"
  }
}
```


## Errrors/Statuses

See relevant spec files.

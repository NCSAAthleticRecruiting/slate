# GET ALL CONTRACTS FOR AN ORGANIZATION

**GET `/api/team_edition/organizations/[:organization_id]/organization_contracts`**

This endpoint retrieves the team edition contracts that an organization has.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Samples**

_cURL_

```shell
curl --request GET \
  "http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/2/organization_contracts")

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
| 200 OK                         | Successfully retrieved teams      |


**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "1",
      "type": "organization-contracts",
      "attributes": {
        "start-date": "2017-02-27",
        "end-date": "2018-02-27",
        "modifier": "0.9",
        "number-of-payments": 3,
        "number-of-teams": 2,
        "number-of-athletes": 0,
        "current-contract-amount": "4968.0",
        "sport-name": "Lacrosse"
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
            "id": "1",
            "type": "sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organization_contracts/1"
      }
    },
    {
      "id": "2",
      "type": "organization-contracts",
      "attributes": {
        "start-date": "2017-02-28",
        "end-date": "2018-02-28",
        "modifier": "1.0",
        "number-of-payments": 1,
        "number-of-teams": 1,
        "number-of-athletes": 0,
        "current-contract-amount": "1560.0",
        "sport-name": "Volleyball"
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
            "id": "2",
            "type": "sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organization_contracts/2"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/2/organization_contracts"
  }
}
```


## Errrors/Statuses

See relevant spec files.

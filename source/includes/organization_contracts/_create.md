# CREATE ORGANIZATION CONTRACT

**POST `/api/team_edition/organizations/:organization_id/organization_contracts`**

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Required Data**
* `type` ('organization_contracts')
* attributes
  - `start_date`
  - `first_payment_date`
  - `number_of_payments`
  - `number_of_teams`
  - `modifier`
  - `amount`
* relationships
  - `organization`
  - `sport`


**Sample Request Body**

```json
{
  "data": {
    "type": "organization_contracts",
    "attributes": {
      "start_date": "2017-02-28",
      "first_payment_date": "2017-02-28",
      "number_of_payments": "2",
      "number_of_teams": "5",
      "modifier": 1,
      "amount": 9300
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "organizations",
          "id": "4"
        }
      },
      "sport": {
        "data": {
          "type": "sports",
          "id": "3"
        }
      }
    }
  }
}
```


**Code Examples**

_cURL_

```shell
curl --request POST \
--url http://qa.ncsasports.org/api/team_edition/organizations/4/organization_contracts \
--header'content-type: application/vnd.api+json' \
--header'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
--data-binary '{"data":{"type":"organization_contracts","attributes":{"start_date":"2017-02-28","first_payment_date":"2017-02-28","number_of_payments":"2","number_of_teams":"5","modifier":1,"amount":9300},"relationships":{"organization":{"data":{"type":"organizations","id":"4"}},"sport":{"data":{"type":"sports","id":"3"}}}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/4/organization_contracts")
options = {"data":{"type":"organization_contracts","attributes":{"start_date":"2017-02-28","first_payment_date":"2017-02-28","number_of_payments":"2","number_of_teams":"5","modifier":1,"amount":9300},"relationships":{"organization":{"data":{"type":"organizations","id":"4"}},"sport":{"data":{"type":"sports","id":"3"}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
/* 201 Created */
{
  "data": {
    "id": "5",
    "type": "organization-contracts",
    "attributes": {
      "start-date": "2017-02-28",
      "end-date": "2018-02-28",
      "modifier": "1.0",
      "number-of-payments": 2,
      "number-of-teams": 5,
      "number-of-athletes": 0,
      "current-contract-amount": "9300.0",
      "sport-name": "Soccer"
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "4",
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
      "self": "/api/team_edition/organization_contracts/5"
    }
  },
  "links": {
    "self": "/api/team_edition/organization_contracts/5"
  }
}
```


## Errrors/Statuses

See relevant spec files.

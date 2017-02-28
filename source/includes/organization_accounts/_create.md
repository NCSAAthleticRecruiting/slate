# CREATE ORGANIZATION ACCOUNT

**POST `/api/team_edition/organizations/:organization_id/organization_accounts`**

This endpoint creates a new organization account.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Sample Request Payload**

```json
{
  "data": {
    "type": "organization_accounts",
    "attributes": {
      "account_holder_first_name": "Joe",
      "account_holder_last_name": "Schmoe",
      "account_holder_email": "joe@schoe.com",
      "united_states": true,
      "billing_zip": "12345",
      "credit_card_number": "1234567891234567",
      "expiration_month": "05",
      "expiration_year": "2025",
      "cvv": "123",
      "phrase": "$2a$10$Dcs9RPCI2nbnkyoA8T1Z7ORkeawNd.Crx1af9r5GSql2QXhipYMuq",
    },
    "relationships": {
      "organization": {
        "data": {
          "type": "organizations",
          "id": 1
        }
      },
      "organization_contract": {
        "data": {
          "type": "organization-contracts",
          "id": 4
        }
      },
      "coach": {
        "data": {
          "type": "coaches",
          "id": 2
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
  --url htttp://qa.ncsasports.org/api/team_edition/organizations/1/organization_accounts \
  --header 'session-token:eyJ0eXAiOiJKV1QiLCiJ9...'\
  --header 'content-type:application/vnd.api+json' \
  --data-binary '{"data":{"type":"organization_accounts","attributes":{"account_holder_first_name":"Joe","account_holder_last_name":"Schmoe","account_holder_email":"joe@schoe.com","united_states":true,"billing_zip":"12345","credit_card_number":"1234567891234567","expiration_month":"05","expiration_year":"2025","cvv":"123","phrase":"$2a$10$Dcs9RPCI2nbnkyoA8T1Z7ORkeawNd.Crx1af9r5GSql2QXhipYMuq"},"relationships":{"organization":{"data":{"type":"organizations", "id": 1}},"organization_contract":{"data":{"type":"organization-contracts","id":4}},"coach": {"data":{"type":"coaches","id":2}}}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = 'htttp://qa.ncsasports.org/api/team_edition/organizations/1/organization_accounts'
options = {"data":{"type":"organization_accounts","attributes":{"account_holder_first_name":"Joe","account_holder_last_name":"Schmoe","account_holder_email":"joe@schoe.com","united_states":true,"billing_zip":"12345","credit_card_number":"1234567891234567","expiration_month":"05","expiration_year":"2025","cvv":"123","phrase":"$2a$10$Dcs9RPCI2nbnkyoA8T1Z7ORkeawNd.Crx1af9r5GSql2QXhipYMuq"},"relationships":{"organization":{"data":{"type":"organizations", "id": 1}},"organization_contract":{"data":{"type":"organization-contracts","id":4}},"coach": {"data":{"type":"coaches","id":2}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request['content-type'] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
/* @TODO */
```

## Errrors/Statuses

See relevant spec files.

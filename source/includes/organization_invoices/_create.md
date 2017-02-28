# CREATE AN INVOICE FOR AN ORGANIZATION

**POST `/api/team_edition/organizations/:organization_id/organization_invoices`**

This endpiont generates and sends an invoice for the organization with the organization_id in the url.

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
    "type": "organization_invoices",
    "relationships": {
      "organization": {
        "data": {
          "type": "organizations",
          "id": "2"
        }
      },
      "organization_contract": {
        "data": {
          "type": "organization_contracts",
          "id": "2"
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
--url http://qa.ncsasports.org/api/team_edition/organizations/2/organization_invoices \
--header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
--header 'content-type: application/vnd.api+json' \
--data-binary '{"data":{"type":"organization_invoices","relationships":{"organization":{"data":{"type":"organizations","id":"2"}},"organization_contract":{"data":{"type":"organization_contracts","id":"2"}}}}}' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/2/organization_invoices")
options = {"data":{"type":"organization_invoices","relationships":{"organization":{"data":{"type":"organizations","id":"2"}},"organization_contract":{"data":{"type":"organization_contracts","id":"2"}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
/* 201 Created */
{}
```

## Errrors/Statuses

| Status        | Response Body                                  | Cause                                                  |
|---------------|------------------------------------------------|--------------------------------------------------------|
| 404 Not Found | `{"details": "No OrganizationContract found"}` | organization_contract with provided id does not exist. |
| 404 Not Found | `{}`                                           | organization with provied id does not exist.           |
| 201 Created   | `{}`                                           | success!                                               |

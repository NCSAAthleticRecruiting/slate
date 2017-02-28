# CREATE AN ORGANIZATION FOR A PARTNER

**POST `/api/team_edition/partners/:partner_id/organizations`**

This endpoint creates an organization.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Required Data**

* attributes
  - `name`
  - `email`
  - `phone`
  - `zip_code`
  - `first_name`
  - `last_name`
* relationships
  - `sport`
    + `type` ('sports')
    + `id`
* type ('organizations')


**Sample Request Payload**

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "John Oliver Athletics",
      "address": "",
      "email": "joliver@example.com",
      "phone": "5558885858",
      "city": "",
      "state": "",
      "zip_code": "46255",
      "website": "",
      "first_name": "John",
      "last_name": "Oliver"
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
            "id": "17708"
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
  --url http://qa.ncsasports.org/api/team_edition/partners/1/organizations \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"organizations","attributes":{"name":"John Oliver Athletics","address":"","email":"joliver@example.com","phone":"5558885858","city":"","state":"","zip_code":"46255","website":"","first_name":"John","last_name":"Oliver"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17708"}]}}}}' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations")
options = {"data":{"type":"organizations","attributes":{"name":"John Oliver Athletics","address":"","email":"joliver@example.com","phone":"5558885858","city":"","state":"","zip_code":"46255","website":"","first_name":"John","last_name":"Oliver"},"relationships":{"partner":{"data":{"type":"partners"}},"sport":{"data":[{"type":"sports","id":"17708"}]}}}}

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
{
  "data": {
    "id": "4",
    "type": "organizations",
    "attributes": {
      "name": "John Oliver Athletics",
      "zip-code": "46255",
      "address": "",
      "city": "",
      "state": "",
      "email": "joliver@example.com",
      "phone": "5558885858",
      "website": "",
      "logo-url": "/images/default_organization_image.png",
      "current-contract-ids": [],
      "sports": [
        "Women's Lacrosse"
      ],
      "primary-contact-name": "Jon Oliver"
    },
    "links": {
      "self": "/api/team_edition/organizations/4"
    }
  }
}
```

## Errrors/Statuses

See relevant spec files.

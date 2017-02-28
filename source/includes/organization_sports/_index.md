# SHOW ALL SPORTS FOR AN ORGANIZATION

**GET `/api/team_edition/organizations/:organization_id/organization_sports`**

This endpoint gets all of an organization's sports.

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
  --url http://qa.ncsasports.org/api/team_edition/organizations/:organization_id/organization_sports \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

<br>

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/organization_sports")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```



## Responses

**Sample Successful Response**

```json
/* 200 OK */
{
  "data": [
    {
      "id": "1",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Women's Volleyball",
        "sport-id": 17696
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organizations/1/organization_sports"
      }
    },
    {
      "id": "2",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Men's Volleyball",
        "sport-id": 17695
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "1",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/organizations/2/organization_sports"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/organization_sports"
  }
}
```


## Errrors/Statuses

See relevant spec files.

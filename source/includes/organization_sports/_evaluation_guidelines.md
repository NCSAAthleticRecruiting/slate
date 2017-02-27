# Get evaluation guidelines

**GET `/api/team_edition/organization_sports/:sport_id/evaluation_guidelines`**

This endpoint retrieves the evaluation guidelines for a given sport in an organization.

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Code Examples**

_cURL_

```shell
curl --request PUT \
  "http://qa.ncsasports.org/api/team_edition/organization_sports/17695/evaluation_guidelines" \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --header 'Content-Type: application/vnd.api+json' \
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organization_sports/17695/evaluation_guidelines")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "sport-17695-evaluation-guidelines",
    "type": "evaluation-guidelines",
    "attributes": {
      "details-url": "https://s3.amazonaws.com/rms-rmfiles-staging/sports_rubricks/All-Sports-Guidelines2016-Mens-Volleyball.pdf",
      "has-details": true,
      "guidelines-summary": {
        "1": [
          "Least Competitive D3"
        ],
        "2": [
          "Somewhat Competitive D3",
          "Least Competitive NAIA"
        ],
        "3": [
          "Least Competitive D2",
          "Competitive D3",
          "Somewhat Competitive NAIA"
        ],
        "4": [
          "Somewhat Competitive to Competitive D2",
          "Most Competitive D3",
          "Competitive NAIA"
        ],
        "5": [
          "Somewhat Competitive D1",
          "Most Competitive D2",
          "Most Competitive NAIA"
        ],
        "6": [
          "Competitive to Most Competitive D1"
        ]
      },
      "sport-id": "17695"
    }
  }
}
```



## Errrors/Statuses

See relevant spec files.

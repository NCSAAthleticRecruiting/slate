# Get evaluation guidelines

**GET `/api/team_edition/organization_sports/:sport_id/evaluation_guidelines`**

### Sample Requests

**cURL**

```shell
curl --request PUT \
  --url http://qa.ncsasports.org/api/team_edition/organization_sports/17695/evaluation_guidelines \
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
```


**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organization_sports/17695/evaluation_guidelines")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

### Sample Response

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

## Get a College

> Sample Successful Request

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/colleges/16038 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{\n  "data": {\n    "type": "organizations",\n    "attributes": {\n      "name": "Test Club Uno",\n      "zip-code": "60642",\n      "address": "234 Maple Lane",\n      "city": "Chicago",\n      "state": "IL",\n      "email": "clubtest@ncsasports.tst",\n      "phone": "1234567899",\n      "website": "http://www.example.com",\n      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"\n    }\n  }\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/colleges/16038")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request.body = "{\n  \"data\": {\n    \"type\": \"organizations\",\n    \"attributes\": {\n      \"name\": \"Test Club Uno\",\n      \"zip-code\": \"60642\",\n      \"address\": \"234 Maple Lane\",\n      \"city\": \"Chicago\",\n      \"state\": \"IL\",\n      \"email\": \"clubtest@ncsasports.tst\",\n      \"phone\": \"1234567899\",\n      \"website\": \"http://www.example.com\",\n      \"logo-url\": \"//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg\"\n    }\n  }\n}"

response = http.request(request)
puts response.read_body
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "16038",
    "type": "colleges",
    "attributes": {
      "name": "NCSA",
      "city": "Fairfax",
      "state": "VA",
      "division": "NCAA I-A",
      "website": "",
      "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/16038college.jpg",
      "sport-ids": [
        17633,
        17634,
        17635,
        17638,
        17639,
        17640,
        17643,
        17645,
        17652,
        17655,
        17659,
        17660,
        17662,
        17665,
        17666,
        17682,
        17683,
        17684,
        17687,
        17688,
        17689,
        17690,
        17691,
        17692,
        17695,
        17696,
        17701,
        17702,
        17706,
        17707,
        17708,
        17711,
        17725
      ]
    }
  },
  "links": {
    "self": "/api/team_edition/colleges/16038"
  }
}
```

GET for retrieving a college resource

### HTTP Request

`GET /api/team_edition/colleges/[:college_id]`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

# SHOW PREFERENCES FOR ATHLETE

**GET `/api/team_edition/athletes/:athlete_id/preferences`**

This endpoint retrieves the athlete's preferences regarding colleegs.

## Requests

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/6/preferences \
  --header 'content-type: application/vnd.api+json'\
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/6/preferences")

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
{
  "data": {
    "id": "6",
    "type": "athlete-preferences",
    "attributes": {
      "athletic-selectivity": [
        "NCAA II",
        "NCAA III",
        "NAIA"
      ],
      "academic-selectivity": [
        "Most Selective"
      ],
      "college-setting": [
        "Urban",
        "Suburban",
        "Rural"
      ],
      "college-type": [
        "Military",
        "Historically Black",
        "Men Only"
      ],
      "major": [
        "Foreign Languages, Literatures, and Linguistics"
      ],
      "enrollment-min": 2000,
      "enrollment-max": 1000000,
      "location": [
        {
          "state": "ME",
          "preference": "maybe"
        },
        {
          "state": "ND",
          "preference": "maybe"
        },
        {
          "state": "OK",
          "preference": "maybe"
        },
        {
          "state": "SD",
          "preference": "maybe"
        },
        {
          "state": "TX",
          "preference": "maybe"
        },
        {
          "state": "WY",
          "preference": "maybe"
        },
        {
          "state": "AR",
          "preference": "maybe"
        },
        {
          "state": "IL",
          "preference": "yes"
        },
        {
          "state": "IN",
          "preference": "yes"
        },
        {
          "state": "ID",
          "preference": "maybe"
        },
        {
          "state": "NV",
          "preference": "maybe"
        },
        {
          "state": "OR",
          "preference": "maybe"
        },
        {
          "state": "UT",
          "preference": "maybe"
        },
        {
          "state": "WA",
          "preference": "maybe"
        }
      ],
      "id": 6
    },
    "relationships": {
      "athlete": {
        "data": {
          "id": 6,
          "type": "athletes"
        }
      }
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/6/preferences"
  }
}
```



## Errors & Statuses

See the relevant spec files to flesh this section out.

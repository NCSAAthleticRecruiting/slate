# GET AN ATHLETE'S PROFILE DATA

**GET `/api/team_edition/athletes/:athlete_id/profile`**

This endpoint gets an athlete's profile data.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Code Examples**

_cURL_

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/6/profile \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/6/profile")

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
    "id": "6",
    "type": "athlete-profiles",
    "attributes": {
      "first-name": "Georgina",
      "last-name": "Buchner-Wilson",
      "email": "mbradberry333@ncsasports.org",
      "ncsa-email": "george.buchner@test.recruitinginfo.org",
      "position": "Kicker",
      "photo-url": "http://s3.amazonaws.com/rms-rmfiles-staging/client_photos/athlete_6904_profile.jpg",
      "ncsa-rating": 5,
      "team-coach-rating": 5.5,
      "team-coach-description": "She's an excellent athlete who consistently performs. We will miss her leadership when she moves on to play at the college level.",
      "height": 75,
      "weight": 90,
      "grad-year": 2018,
      "key-stats-count": 13,
      "key-stats-total": 4,
      "transcript": true,
      "gpa": true,
      "sat": true,
      "act": true,
      "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/573275?session_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdXRob3JpemVkX2NsaWVudF9pZHMiOls1NzMyNzVdLCJleHAiOjE0OTAzODQ4NDB9.ZhXdTolsW3eSejgJ5YCK1WMcctGZvwfwjF82lCdNPN0",
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
    "self": "/api/team_edition/athletes/6/profile"
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

## Get an Athlete

> Sample Successful Request

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "1",
    "type": "athletes",
    "attributes": {
      "organization-id": 10,
      "client-id": 774974,
      "primary-team-name": "Team Alpha",
      "profile": {
        "first-name": "KIM",
        "last-name": "ZMESKAL",
        "position": "Libero",
        "photo-url": "http://s3.amazonaws.com/rms-rmfiles-staging/client_photos/athlete_4455_profile.jpg",
        "rating": 6,
        "height": 63,
        "weight": 130,
        "grad-year": 2017,
        "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/774974?session_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpZCI6MTksInBocmFzZSI6IiQyYSQxMCRidkxoMTRwRFNNQTNmR2ZydktkY01lUlhBUVBoQzVuWTZ2SUVZSDl6OW1HZXQxUUdOMEEveSIsIm9yZ2FuaXphdGlvbl9pZCI6OSwidXNlcl9maXJzdF9uYW1lIjoiSm9zaCIsInVzZXJfbGFzdF9uYW1lIjoiTG9ja2hhcnQiLCJhdXRob3JpemVkX2NsaWVudF9pZHMiOls3NzQ2NTIsNzcxNzc4XSwiZXhwIjoxNDgzOTEyNjk4fQ.uIPyYtSENtbfu1NyZfQqageg3q5iY2lktcmR46cv7VU"
      },
      "activity": {
        "last-login": "2016-08-11T10:38:13.450-05:00",
        "video-updated-at": "2016-06-22T16:53:00.940-05:00",
        "colleges": [
          {
            "college-id": "15568",
            "college-name": "University of California - Los Angeles",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Los Angeles",
            "college-state": "CA",
            "college-state-name": "CALIFORNIA",
            "match-percentage": 92,
            "last-activity-date": "2016-08-11T12:00:07.000-05:00",
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15568college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": true,
            "activity-summary": {
              "follows-count": 1,
              "profile-views-count": 2,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          },
          {
            "college-id": "14552",
            "college-name": "Harvard University",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Cambridge",
            "college-state": "MA",
            "college-state-name": "MASSACHUSETTS",
            "match-percentage": 85,
            "last-activity-date": null,
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17600college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": false,
            "activity-summary": {
              "follows-count": 0,
              "profile-views-count": 0,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          },
          {
            "college-id": "15156",
            "college-name": "Pepperdine University",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Malibu",
            "college-state": "CA",
            "college-state-name": "CALIFORNIA",
            "match-percentage": 87,
            "last-activity-date": null,
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15156college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": false,
            "activity-summary": {
              "follows-count": 0,
              "profile-views-count": 0,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          },
          {
            "college-id": "15193",
            "college-name": "Princeton University",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Princeton",
            "college-state": "NJ",
            "college-state-name": "NEW JERSEY",
            "match-percentage": 90,
            "last-activity-date": null,
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/19603college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": false,
            "activity-summary": {
              "follows-count": 0,
              "profile-views-count": 0,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          },
          {
            "college-id": "15449",
            "college-name": "Stanford University",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Stanford",
            "college-state": "CA",
            "college-state-name": "CALIFORNIA",
            "match-percentage": 84,
            "last-activity-date": null,
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15449college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": false,
            "activity-summary": {
              "follows-count": 0,
              "profile-views-count": 0,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          },
          {
            "college-id": "15595",
            "college-name": "University of California - Irvine",
            "division-name": "NCAA I",
            "division-display-order": 30,
            "college-city": "Irvine",
            "college-state": "CA",
            "college-state-name": "CALIFORNIA",
            "match-percentage": 86,
            "last-activity-date": null,
            "team-coach-recommended": false,
            "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13312college.jpg",
            "ncsa-match": true,
            "athlete-interested": true,
            "college-activity": false,
            "activity-summary": {
              "follows-count": 0,
              "profile-views-count": 0,
              "athlete-received-emails-count": 0,
              "athlete-sent-emails-count": 0
            }
          }
        ]
      }
    },
    "relationships": {
      "organization": {
        "data": {
          "id": "10",
          "type": "organizations"
        }
      }
    },
    "links": {
      "self": "/api/team_edition/athletes/1"
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/1"
  }
}
```

GET for retrieving an athlete resource

### HTTP Request

`GET /api/team_edition/athletes/[:athlete_id]`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

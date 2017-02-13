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
        "email": "example@email.com",
        "ncsa-email": "example@ncsa.com",
        "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/774974?session_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpZCI6MTksInBocmFzZSI6IiQyYSQxMCRidkxoMTRwRFNNQTNmR2ZydktkY01lUlhBUVBoQzVuWTZ2SUVZSDl6OW1HZXQxUUdOMEEveSIsIm9yZ2FuaXphdGlvbl9pZCI6OSwidXNlcl9maXJzdF9uYW1lIjoiSm9zaCIsInVzZXJfbGFzdF9uYW1lIjoiTG9ja2hhcnQiLCJhdXRob3JpemVkX2NsaWVudF9pZHMiOls3NzQ2NTIsNzcxNzc4XSwiZXhwIjoxNDgzOTEyNjk4fQ.uIPyYtSENtbfu1NyZfQqageg3q5iY2lktcmR46cv7VU",
        "photo-url": "http://s3.amazonaws.com/rms-rmfiles-staging/client_photos/athlete_4455_profile.jpg",
        "position": "Libero",
        "ncsa-rating": 5,
        "team-coach-rating": 6,
        "team-coach-description": "This is the best athlete ever!",
        "grad-year": 2017,
        "height": 63,
        "weight": 130,
        "key-stats-count": 3,
        "key-stats-total": 4,
        "transcript": true,
        "gpa": true,
        "sat": true,
        "act": true,
      },
      "activity": {
        "video-updated-at": "2016-06-22T16:53:00.940-05:00",
        "last-login": "2016-08-11T10:38:13.450-05:00",
        "last-email-sent-at": "2016-06-11T10:38:13.450-05:00",
        "athlete-sent-emails-count": 4,
        "athlete-received-emails-count": 1,
        "follows-count": 12,
        "profile-views-count": 40,
        "last-coach-activity-date": "2016-08-11T12:00:07.000-05:00",
        "weekly-activity": [
          {
            "weeks-ago": 0,
            "view-count": 1,
            "follow-count": 1,
            "message-received-count": 0
          },
          {
            "weeks-ago": 1,
            "view-count": 6,
            "follow-count": 3,
            "message-received-count": 1
          },
          {
            "weeks-ago": 2,
            "view-count": 10,
            "follow-count": 5,
            "message-received-count": 0
          },
          {
            "weeks-ago": 3,
            "view-count": 12,
            "follow-count": 3,
            "message-received-count": 0
          },
          {
            "weeks-ago": 4,
            "view-count": 11,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 5,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 6,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 7,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 8,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 9,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 10,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          },
          {
            "weeks-ago": 11,
            "view-count": 0,
            "follow-count": 0,
            "message-received-count": 0
          }
        ],
        "colleges": [
          {
            "college-name": "University of California - Los Angeles",
            "college-id": "15568",
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
      },
      "preferences": {
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
            "state": "MD",
            "preference": "maybe"
          },
          {
            "state": "MA",
            "preference": "yes"
          },
          {
            "state": "NY",
            "preference": "yes"
          },
          {
            "state": "OH",
            "preference": "maybe"
          },
          {
            "state": "PA",
            "preference": "maybe"
          },
          {
            "state": "VA",
            "preference": "maybe"
          },
          {
            "state": "WV",
            "preference": "maybe"
          },
          {
            "state": "DC",
            "preference": "maybe"
          },
          {
            "state": "KS",
            "preference": "maybe"
          },
          {
            "state": "NE",
            "preference": "maybe"
          },
          {
            "state": "NM",
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
            "state": "IA",
            "preference": "maybe"
          },
          {
            "state": "KY",
            "preference": "maybe"
          },
          {
            "state": "MI",
            "preference": "yes"
          },
          {
            "state": "MN",
            "preference": "yes"
          },
          {
            "state": "MO",
            "preference": "maybe"
          },
          {
            "state": "TN",
            "preference": "maybe"
          },
          {
            "state": "WI",
            "preference": "yes"
          },
          {
            "state": "AL",
            "preference": "maybe"
          },
          {
            "state": "FL",
            "preference": "maybe"
          },
          {
            "state": "GA",
            "preference": "maybe"
          },
          {
            "state": "LA",
            "preference": "maybe"
          },
          {
            "state": "MS",
            "preference": "maybe"
          },
          {
            "state": "NC",
            "preference": "maybe"
          },
          {
            "state": "SC",
            "preference": "maybe"
          },
          {
            "state": "CT",
            "preference": "yes"
          },
          {
            "state": "DE",
            "preference": "maybe"
          },
          {
            "state": "NH",
            "preference": "yes"
          },
          {
            "state": "NJ",
            "preference": "maybe"
          },
          {
            "state": "RI",
            "preference": "yes"
          },
          {
            "state": "VT",
            "preference": "yes"
          },
          {
            "state": "MT",
            "preference": "maybe"
          },
          {
            "state": "CO",
            "preference": "maybe"
          },
          {
            "state": "AK",
            "preference": "maybe"
          },
          {
            "state": "AZ",
            "preference": "maybe"
          },
          {
            "state": "CA",
            "preference": "yes"
          },
          {
            "state": "HI",
            "preference": "maybe"
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
        ]
      },
      "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/573275?session_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJhdXRob3JpemVkX2NsaWVudF9pZHMiOls1NzMyNzVdLCJleHAiOjE0ODk0MjIwOTR9.eC1_QHB7zu1H7yfJdn8iO3wSTAyxsrzTexcAVOHjNfY"
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

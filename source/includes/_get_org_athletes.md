## Get an Organization's Athletes

> Sample Successful Request:

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/athletes")

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
  "data": [
    {
      "id": "5",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 771534,
        "primary-team-name": "18 Elite",
        "sport-id": 17696,
        "profile": {
          "first-name": "GdillonMurphy",
          "last-name": "Murphy",
          "email": "gdillonmurphy@gmail.com",
          "ncsa-email": "gdillonmurphy.murphy@test.recruitinginfo.org",
          "position": "Opposite",
          "photo-url": "http://s3.amazonaws.com/rms-rmfiles-staging/client_photos/athlete_2999_profile.jpg",
          "ncsa-rating": 0,
          "team-coach-rating": 5,
          "team-coach-description": "",
          "height": 66,
          "weight": 170,
          "grad-year": 2015,
          "key-stats-count": 0,
          "key-stats-total": 2,
          "transcript": false,
          "gpa": true,
          "sat": true,
          "act": true
        },
        "activity": {
          "last-login": "2017-01-30T12:55:55.503-06:00",
          "video-updated-at": "2015-10-06T15:37:30.330-05:00",
          "last-email-sent-at": null,
          "profile-views-count": 166,
          "follows-count": 32,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 1,
          "last-coach-activity-date": "2017-01-23T15:36:20.050-06:00",
          "weekly-activity": [
            {
              "client-id": 771534,
              "weeks-ago": 5,
              "follow-count": 0,
              "view-count": 2,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 8,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 11,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 10,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 2,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 1,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 7,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 4,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 3,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 9,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 0,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 6,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            }
          ],
          "colleges": []
        },
        "preferences": {
          "athletic-selectivity": [],
          "academic-selectivity": [],
          "college-setting": [],
          "college-type": [],
          "major": [],
          "enrollment-min": null,
          "enrollment-max": null,
          "location": []
        },
        "ncsa-profile-url": null
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
        "self": "/api/team_edition/athletes/5"
      }
    },
    {
      "id": "7",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 18132,
        "primary-team-name": "18 Elite",
        "sport-id": 17696,
        "profile": {
          "first-name": "Chris",
          "last-name": "Heineken",
          "email": "chris.hein@ncsasports.tst",
          "ncsa-email": "chris.hein1@test.recruitinginfo.org",
          "position": "Outside Hitter",
          "photo-url": "http://s3.amazonaws.com/rms-rmfiles-staging/client_photos/athlete_6803_profile.jpg",
          "ncsa-rating": 5,
          "team-coach-rating": 5.5,
          "team-coach-description": "Test",
          "height": 52,
          "weight": 270,
          "grad-year": 2018,
          "key-stats-count": 4,
          "key-stats-total": 2,
          "transcript": true,
          "gpa": true,
          "sat": true,
          "act": true
        },
        "activity": {
          "last-login": "2017-01-31T08:59:02.253-06:00",
          "video-updated-at": "2016-12-15T11:12:43.087-06:00",
          "last-email-sent-at": null,
          "profile-views-count": 1875,
          "follows-count": 34,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 2740,
          "last-coach-activity-date": "2017-01-06T09:08:52.000-06:00",
          "weekly-activity": [
            {
              "client-id": 18132,
              "weeks-ago": 6,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 9,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 3,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 0,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 10,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 4,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 1,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 7,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 2,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 8,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 11,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 18132,
              "weeks-ago": 5,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            }
          ],
          "colleges": []
        },
        "preferences": {
          "athletic-selectivity": [],
          "academic-selectivity": [],
          "college-setting": [],
          "college-type": [],
          "major": [],
          "enrollment-min": null,
          "enrollment-max": null,
          "location": []
        },
        "ncsa-profile-url": null
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
        "self": "/api/team_edition/athletes/7"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/athletes"
  }
}
```

GET for retrieving all athlete resources from an organization

### HTTP Request

`GET /api/team_edition/organizations/[:organization_id]/athletes`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

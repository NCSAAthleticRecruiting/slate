# GET ALL ATHLETES FOR ORGANIZATION

**GET `/api/team_edition/organizations/:organization_id/athletes`**


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
  "http://qa.ncsasports.org/api/team_edition/organizations/1/athletes" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/athletes")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Response Types**

| Status Code                    | Description/Cause                 |
|--------------------------------|-----------------------------------|
| 200 OK                         | Successfully retrieved athletess   |


**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "46",
      "type": "athletes",
      "attributes": {
        "organization-id": 2,
        "client-id": 776104,
        "primary-team-name": "Conan's Volleyball Team",
        "sport-id": 17696,
        "profile": {
          "first-name": "Claire",
          "last-name": "Murphy",
          "email": "claire.murphy@ncsanavtest.test",
          "ncsa-email": "claire.murphy@test.recruitinginfo.org",
          "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/773223"
          "photo-url": "/images/default_user_image.png",
          "position": "Middle Hitter",
          "ncsa-rating": 0,
          "team-coach-rating": 5,
          "team-coach-description": "Claire is a great team leader with good sportsmanship.",
          "grad-year": 2019,
          "height": 70,
          "weight": 120,
          "key-stats-count": 3,
          "key-stats-total": 4,
          "transcript": false,
          "gpa": true,
          "sat": false,
          "act": false
        },
        "activity": {
          "video-updated-at": "2016-08-19T17:17:55.873-05:00",
          "last-login": "2017-02-09T14:42:02.737-06:00",
          "last-email-sent-at": "2017-02-09T14:42:02.737-06:00",
          "athlete-sent-emails-count": 22,
          "athlete-received-emails-count": 15,
          "follows-count": 12,
          "profile-views-count": 44,
          "last-coach-activity-date": "2017-02-09T14:44:05.160-06:00",
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 5,
              "follow-count": 1,
              "message-received-count": 1
            },
            {
              "weeks-ago": 1,
              "view-count": 5,
              "follow-count": 0,
              "message-received-count": 1
            },
            {
              "weeks-ago": 2,
              "view-count": 8,
              "follow-count": 3,
              "message-received-count": 2
            },
            {
              "weeks-ago": 3,
              "view-count": 4,
              "follow-count": 1,
              "message-received-count": 1
            },
            {
              "weeks-ago": 4,
              "view-count": 4,
              "follow-count": 2,
              "message-received-count": 1
            },
            {
              "weeks-ago": 5,
              "view-count": 3,
              "follow-count": 0,
              "message-received-count": 2
            },
            {
              "weeks-ago": 6,
              "view-count": 1,
              "follow-count": 0,
              "message-received-count": 1
            },
            {
              "weeks-ago": 7,
              "view-count": 1,
              "follow-count": 1,
              "message-received-count": 1
            },
            {
              "weeks-ago": 8,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 9,
              "view-count": 1,
              "follow-count": 1,
              "message-received-count": 1
            },
            {
              "weeks-ago": 10,
              "view-count": 3,
              "follow-count": 0,
              "message-received-count": 1
            },
            {
              "weeks-ago": 11,
              "view-count": 9,
              "follow-count": 3,
              "message-received-count": 3
            }
          ],
          "colleges": []
        },
        "preferences": {
          "athletic-selectivity": [
            "NCAA I",
            "NCAA II"
          ],
          "academic-selectivity": [
            "Selective",
            "Somewhat Selective"
          ],
          "college-setting": [
            "Urban",
            "Rural"
          ],
          "college-type": [
            "Military"
          ],
          "major": [
            "Physics"
          ],
          "enrollment-min": null,
          "enrollment-max": null,
          "location": [
            {
              "state": "WI",
              "preference": "maybe"
            },
            {
              "state": "CO",
              "preference": "yes"
            },
            {
              "state": "KS",
              "preference": "yes"
            },
          ]
        },
        "ncsa-profile-url": "http://qa.ncsasports.org/clientrms/athletes/773223",
        "deleted": false
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "2",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/athletes/2"
      }
    },
    {
      "id": "45",
      "type": "athletes",
      "attributes": {
        "organization-id": 2,
        "client-id": 776103,
        "primary-team-name": "Conan's Volleyball Team",
        "sport-id": 17696,
        "profile": {
          "first-name": "Jill",
          "last-name": "O'Connor",
          "email": "hellojillo@example.com",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": "Center",
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2020,
          "height": null,
          "weight": null,
          "key-stats-count": null,
          "key-stats-total": null,
          "transcript": null,
          "gpa": null,
          "sat": null,
          "act": null
        },
        "activity": {
          "video-updated-at": null,
          "last-login": "2017-01-24T11:22:24.247-05:00",
          "last-email-sent-at": "2017-01-22T11:22:24.247-05:00",
          "athlete-sent-emails-count": 2,
          "athlete-received-emails-count": 6,
          "follows-count": 6,
          "profile-views-count": 15,
          "last-coach-activity-date": "2017-01-22T11:22:2.247-05:00",
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 1,
              "follow-count": 1,
              "message-received-count": 3
            },
            {
              "weeks-ago": 1,
              "view-count": 4,
              "follow-count": 1,
              "message-received-count": 1
            },
            {
              "weeks-ago": 2,
              "view-count": 10,
              "follow-count": 4,
              "message-received-count": 2
            },
            {
              "weeks-ago": 3,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 4,
              "view-count": 0,
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
        "ncsa-profile-url": null,
        "deleted": false
      },
      "relationships": {
        "organization": {
          "data": {
            "id": "2",
            "type": "organizations"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/athletes/45"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/2/athletes"
  }
}
```


# GET ACTIVITY FOR ATHLETE

**GET `/api/team_edition/athletes/:athlete_id/activity`**

This endpoint retrieves the athlete's activity history & stats

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
  --url http://qa.ncsasports.org/api/team_edition/athletes/6/activity \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/6/activity")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9..'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "9",
    "type": "athlete-activities",
    "attributes": {
      "last-login": "2017-01-30T12:55:55.503-06:00",
      "video-updated-at": "2017-01-06T15:37:30.330-05:00",
      "last-email-sent-at": "2017-01-30T12:55:55.503-06:00",
      "profile-views-count": 166,
      "follows-count": 32,
      "athlete-sent-emails-count": 42,
      "athlete-received-emails-count": 57,
      "last-coach-activity-date": "2017-02-27T15:36:20.050-06:00",
      "weekly-activity": [
        {
          "weeks-ago": 0,
          "view-count": 10,
          "follow-count": 2,
          "message-received-count": 8
        },
        {
          "weeks-ago": 1,
          "view-count": 9,
          "follow-count": 4,
          "message-received-count": 6
        },
        {
          "weeks-ago": 2,
          "view-count": 12,
          "follow-count": 4,
          "message-received-count": 5
        },
        {
          "weeks-ago": 3,
          "view-count": 7,
          "follow-count": 2,
          "message-received-count": 3
        },
        {
          "weeks-ago": 4,
          "view-count": 7,
          "follow-count": 1,
          "message-received-count": 1
        },
        {
          "weeks-ago": 5,
          "view-count": 14,
          "follow-count": 5,
          "message-received-count": 7
        },
        {
          "weeks-ago": 6,
          "view-count": 10,
          "follow-count": 5,
          "message-received-count": 6
        },
        {
          "weeks-ago": 7,
          "view-count": 22,
          "follow-count": 10,
          "message-received-count": 11
        },
        {
          "weeks-ago": 8,
          "view-count": 4,
          "follow-count": 2,
          "message-received-count": 4
        },
        {
          "weeks-ago": 9,
          "view-count": 5,
          "follow-count": 4,
          "message-received-count": 2
        },
        {
          "weeks-ago": 10,
          "view-count": 3,
          "follow-count": 2,
          "message-received-count": 3
        },
        {
          "weeks-ago": 11,
          "view-count": 2,
          "follow-count": 1,
          "message-received-count": 2
        }
      ],
      "colleges": [
        {
          "college-id": "15627",
          "college-name": "University of Illinois at Chicago",
          "division-name": "NCAA I",
          "division-display-order": 30,
          "college-city": "Chicago",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": null,
          "last-activity-date": "2017-01-09T14:15:05.000-06:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15627college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 13,
            "profile-views-count": 22,
            "athlete-received-emails-count": 8,
            "athlete-sent-emails-count": 8
          }
        },
        {
          "college-id": "13917",
          "college-name": "Arizona State University",
          "division-name": "NCAA I",
          "division-display-order": 30,
          "college-city": "Tempe",
          "college-state": "AZ",
          "college-state-name": "ARIZONA",
          "match-percentage": null,
          "last-activity-date": "2011-03-29T01:03:52.000-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13917college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 6,
            "profile-views-count": 11,
            "athlete-received-emails-count": 4,
            "athlete-sent-emails-count": 3
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
          "match-percentage": null,
          "last-activity-date": null,
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15449college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 13,
            "profile-views-count": 28,
            "athlete-received-emails-count": 12,
            "athlete-sent-emails-count": 15
          }
        },
        {
          "college-id": "13935",
          "college-name": "Augustana College - Illinois",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Rock Island",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": null,
          "last-activity-date": "2016-10-11T11:08:11.107-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13021college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 5,
            "profile-views-count": 15,
            "athlete-received-emails-count": 22,
            "athlete-sent-emails-count": 16
          }
        }
      ],
      "id": 9
    },
    "relationships": {
      "athlete": {
        "data": {
          "id": 9,
          "type": "athletes"
        }
      }
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/9/activity"
  }
}
```



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

```json
{
  "errors": [
    {
      "status": 401,
      "source": {
        "pointer": "/api/team_edition/athletes/6/activity"
      },
      "detail": "Unauthorized"
    }
  ]
}
```

# REFRESH ATHLETE DATA

**GET `/api/team_edition/organizations/[:organization_id]/refresh_athletes`**

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
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/refresh_athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/refresh_athletes")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
{
  "data": [
    {
      "id": "18",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 90034,
        "primary-team-name": "16 Elite",
        "sport-id": 17695,
        "profile": {
          "first-name": "Hilton",
          "last-name": "Nader",
          "email": "alfred@konopelski.us",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2021,
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
          "last-login": null,
          "last-email-sent-at": null,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 0,
          "follows-count": 0,
          "profile-views-count": 0,
          "last-coach-activity-date": null,
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 1,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 2,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
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
        "self": "/api/team_edition/athletes/18"
      }
    },
    {
      "id": "9",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 44457,
        "primary-team-name": "18 Elite",
        "sport-id": 17696,
        "profile": {
          "first-name": "Latesha",
          "last-name": "Haag",
          "email": "londa@schoenmckenzie.us",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
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
          "last-login": null,
          "last-email-sent-at": null,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 0,
          "follows-count": 0,
          "profile-views-count": 0,
          "last-coach-activity-date": null,
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 1,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 2,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
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
        "self": "/api/team_edition/athletes/9"
      }
    },
    {
      "id": "43",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": null,
        "primary-team-name": "Women's Traveling Elite",
        "sport-id": 17696,
        "profile": {
          "first-name": "Marine",
          "last-name": "Nil client id",
          "email": "damon@deckow.co.uk",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2021,
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
          "last-login": null,
          "last-email-sent-at": null,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 0,
          "follows-count": 0,
          "profile-views-count": 0,
          "last-coach-activity-date": null,
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 1,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 2,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
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
        "self": "/api/team_edition/athletes/43"
      }
    },
    {
      "id": "44",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": null,
        "primary-team-name": "Men's Traveling Elite",
        "sport-id": 17695,
        "profile": {
          "first-name": "Tu",
          "last-name": "Nil client id",
          "email": "robby@hagenesbednar.com",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2021,
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
          "last-login": null,
          "last-email-sent-at": null,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 0,
          "follows-count": 0,
          "profile-views-count": 0,
          "last-coach-activity-date": null,
          "weekly-activity": [
            {
              "weeks-ago": 0,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 1,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
            },
            {
              "weeks-ago": 2,
              "view-count": 0,
              "follow-count": 0,
              "message-received-count": 0
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
        "self": "/api/team_edition/athletes/44"
      }
    },
    {
      "id": "6",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 573275,
        "primary-team-name": "18 Elite",
        "sport-id": 17696,
        "profile": {
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
          "act": true
        },
        "activity": {
          "last-login": "2017-02-19T15:56:06.777-06:00",
          "video-updated-at": "2017-01-03T14:46:04.763-06:00",
          "last-email-sent-at": null,
          "profile-views-count": 824,
          "follows-count": 15,
          "athlete-sent-emails-count": 0,
          "athlete-received-emails-count": 29,
          "last-coach-activity-date": "2017-02-06T16:54:44.533-06:00",
          "weekly-activity": [
            {
              "client-id": 573275,
              "weeks-ago": 2,
              "follow-count": 0,
              "view-count": 3,
              "message-received-count": 4
            },
            {
              "client-id": 573275,
              "weeks-ago": 6,
              "follow-count": 1,
              "view-count": 1,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 7,
              "follow-count": 1,
              "view-count": 1,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 1,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 10,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 4,
              "follow-count": 1,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 9,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 11,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 3,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 0,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 5,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            },
            {
              "client-id": 573275,
              "weeks-ago": 8,
              "follow-count": 0,
              "view-count": 0,
              "message-received-count": 0
            }
          ],
          "colleges": [
            {
              "college-name": "Northern Illinois University",
              "college-id": "15036",
              "division-name": "NCAA I-A",
              "division-display-order": 10,
              "college-city": "Dekalb",
              "college-state": "IL",
              "college-state-name": "ILLINOIS",
              "match-percentage": 22,
              "last-activity-date": "2016-12-09T15:15:04.000-06:00",
              "team-coach-recommended": true,
              "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15036college.jpg",
              "ncsa-match": false,
              "athlete-interested": false,
              "college-activity": true,
              "activity-summary": {
                "follows-count": 0,
                "profile-views-count": 1,
                "athlete-received-emails-count": 1,
                "athlete-sent-emails-count": 0
              }
            },
            {
              "college-name": "University of Illinois at Urbana-Champaign",
              "college-id": "15626",
              "division-name": "NCAA I-A",
              "division-display-order": 10,
              "college-city": "Champaign",
              "college-state": "IL",
              "college-state-name": "ILLINOIS",
              "match-percentage": 88,
              "last-activity-date": "2017-01-12T13:40:06.767-06:00",
              "team-coach-recommended": true,
              "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15626college.jpg",
              "ncsa-match": true,
              "athlete-interested": true,
              "college-activity": true,
              "activity-summary": {
                "follows-count": 2,
                "profile-views-count": 9,
                "athlete-received-emails-count": 7,
                "athlete-sent-emails-count": 0
              }
            },
            {
              "college-name": "Robert Morris University - Illinois",
              "college-id": "15235",
              "division-name": "NAIA",
              "division-display-order": 60,
              "college-city": "Chicago",
              "college-state": "IL",
              "college-state-name": "ILLINOIS",
              "match-percentage": 0,
              "last-activity-date": "2017-02-13T16:30:02.000-06:00",
              "team-coach-recommended": true,
              "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15235college.jpg",
              "ncsa-match": false,
              "athlete-interested": false,
              "college-activity": true,
              "activity-summary": {
                "follows-count": 1,
                "profile-views-count": 0,
                "athlete-received-emails-count": 1,
                "athlete-sent-emails-count": 0
              }
            },
            {
              "college-name": "Augustana College - Illinois",
              "college-id": "13935",
              "division-name": "NCAA III",
              "division-display-order": 50,
              "college-city": "Rock Island",
              "college-state": "IL",
              "college-state-name": "ILLINOIS",
              "match-percentage": 35,
              "last-activity-date": "2017-02-13T13:15:04.000-06:00",
              "team-coach-recommended": true,
              "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13021college.jpg",
              "ncsa-match": false,
              "athlete-interested": true,
              "college-activity": true,
              "activity-summary": {
                "follows-count": 1,
                "profile-views-count": 50,
                "athlete-received-emails-count": 5,
                "athlete-sent-emails-count": 0
              }
            },
            {
              "college-name": "University of California - Los Angeles",
              "college-id": "15568",
              "division-name": "NCAA I-A",
              "division-display-order": 10,
              "college-city": "Los Angeles",
              "college-state": "CA",
              "college-state-name": "CALIFORNIA",
              "match-percentage": 60,
              "last-activity-date": "2016-10-05T10:00:14.000-05:00",
              "team-coach-recommended": true,
              "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15568college.jpg",
              "ncsa-match": false,
              "athlete-interested": true,
              "college-activity": true,
              "activity-summary": {
                "follows-count": 3,
                "profile-views-count": 140,
                "athlete-received-emails-count": 1,
                "athlete-sent-emails-count": 0
              }
            }
          ]
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
        "self": "/api/team_edition/athletes/6"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/athletes"
  }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

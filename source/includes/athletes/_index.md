# Show Athletes
<br>

## _Overview_

* `GET /api/team_edition/organizations/[:organization_id]/athletes`

* Request Headers
  * `Content-Type`: `application/vnd.api+json`
  * `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`

<br>
## _Sample Successful Requests_

#### 1. cURL

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/athlete")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

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
          "key-stats-total": 4,
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
              "weeks-ago": 6,
              "follow-count": 0,
              "view-count": 2,
              "message-received-count": 0
            },
            {
              "client-id": 771534,
              "weeks-ago": 5,
              "follow-count": 0,
              "view-count": 0,
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
        "self": "/api/team_edition/athletes/6"
      }
    },
    {
      "id": "13",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 82398,
        "primary-team-name": "16 Elite",
        "sport-id": 17695,
        "profile": {
          "first-name": "Evelynn",
          "last-name": "Schiller",
          "email": "yolanda.okon@johnston.com",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2022,
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
        "self": "/api/team_edition/athletes/13"
      }
    },
    {
      "id": "12",
      "type": "athletes",
      "attributes": {
        "organization-id": 1,
        "client-id": 56341,
        "primary-team-name": "16 Elite",
        "sport-id": 17695,
        "profile": {
          "first-name": "Danny",
          "last-name": "Bartell",
          "email": "denis_kautzer@dickinson.us",
          "ncsa-email": null,
          "ncsa-profile-url": null,
          "photo-url": "/images/default_user_image.png",
          "position": null,
          "ncsa-rating": null,
          "team-coach-rating": null,
          "team-coach-description": null,
          "grad-year": 2023,
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
        "self": "/api/team_edition/athletes/12"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/athletes"
  }
}
```




### Miscellaneous

**Help with JSON API Requests**

* <a href="http://jsonapi.org/format/#crud-creating">Creating a RESOURCE</a>
* <a href="http://jsonapi.org/format/#crud-updating">Updating a RESOURCE</a>
* <a href="http://jsonapi.org/format/#crud-updating-relationships">Updating RESOURCE Relationships</a>
* <a href="http://jsonapi.org/format/#crud-deleting">Deleting a RESOURCE</a>


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The resource requested is hidden for administrators only
404 | Not Found -- The specified resource could not be found
405 | Method Not Allowed -- You tried to access a resource with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The resource requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many resources! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.


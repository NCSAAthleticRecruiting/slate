# GET A COLLEGE

**GET `/api/team_edition/organizations/:organization_id/colleges/:college_id`**

This endpoint gets a college's detailed information.

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
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/colleges/16038 \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --header 'content-type: application/vnd.api+json' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/colleges/16038")

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
        "id": "16038",
        "type": "colleges",
        "attributes": {
            "name": "NCSA",
            "city": "Fairfax",
            "state": "VA",
            "division": "NCAA I",
            "website": null,
            "type": "HIDDEN",
            "private-or-public": "PUBLIC",
            "location-type": "",
            "academic-strength": 1,
            "tuition-instate": "",
            "tuition-outofstate": "",
            "enrollment": null,
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
            ],
            "coaches": [
                {
                    "name": "Coach Test31754",
                    "position": "",
                    "phone-number": "",
                    "email": "coach31754@ncsasports.tst"
                }
            ],
            "activity": [
                {
                    "id": "7",
                    "team-name": "18 Elite",
                    "first-name": "Chris",
                    "last-name": "Heineken",
                    "email": "chris.hein@ncsasports.tst",
                    "ncsa-email": "chris.hein1@test.recruitinginfo.org",
                    "position": "Outside Hitter",
                    "grad-year": "2018",
                    "photo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18132clid.jpg",
                    "athlete-interested": false,
                    "team-coach-recommended": false,
                    "match-percentage": null,
                    "last-activity": {
                        "last-profile-view-date": "2013-03-01T19:37:51.540-06:00",
                        "coach-first-name": "Coach",
                        "coach-last-name": "Test36033",
                        "coach-position": "",
                        "coach-recent-action": "view",
                        "last-activity-date": "2013-03-01T19:37:51.540-06:00"
                    },
                    "activity-summary": {
                        "follows-count": 0,
                        "profile-views-count": 40,
                        "athlete-sent-emails-count": 0,
                        "athlete-received-emails-count": 2
                    }
                },
                {
                    "id": "6",
                    "team-name": "18 Elite",
                    "first-name": "Georgina",
                    "last-name": "Buchner-Wilson",
                    "email": "mbradberry333@ncsasports.org",
                    "ncsa-email": "george.buchner@test.recruitinginfo.org",
                    "position": "Kicker",
                    "grad-year": "2018",
                    "photo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/573275clid.jpg",
                    "athlete-interested": false,
                    "team-coach-recommended": false,
                    "match-percentage": null,
                    "last-activity": {
                        "last-profile-view-date": null,
                        "coach-first-name": "Matt",
                        "coach-last-name": "Roe",
                        "coach-position": "",
                        "coach-recent-action": "follow",
                        "last-activity-date": "2016-03-18T13:37:13.003-05:00"
                    },
                    "activity-summary": {
                        "follows-count": 2,
                        "profile-views-count": 0,
                        "athlete-sent-emails-count": 0,
                        "athlete-received-emails-count": 1
                    }
                },
                {
                    "id": "5",
                    "team-name": "18 Elite",
                    "first-name": "GdillonMurphy",
                    "last-name": "Murphy",
                    "email": "gdillonmurphy@gmail.com",
                    "ncsa-email": "gdillonmurphy.murphy@test.recruitinginfo.org",
                    "position": "Opposite",
                    "grad-year": "2015",
                    "photo-url": "/images/default_user_image.png",
                    "athlete-interested": false,
                    "team-coach-recommended": false,
                    "match-percentage": null,
                    "last-activity": {
                        "last-profile-view-date": null,
                        "coach-first-name": "Coach",
                        "coach-last-name": "Test36033",
                        "coach-position": "",
                        "coach-recent-action": "follow",
                        "last-activity-date": "2015-06-01T00:00:00.000-05:00"
                    },
                    "activity-summary": {
                        "follows-count": 1,
                        "profile-views-count": 0,
                        "athlete-sent-emails-count": 0,
                        "athlete-received-emails-count": 0
                    }
                },
                {
                    "id": "4",
                    "team-name": "18 Elite",
                    "first-name": "Jacquelyn",
                    "last-name": "Smith",
                    "email": "jhailey0505@comcast.net",
                    "ncsa-email": null,
                    "position": "Libero",
                    "grad-year": "2018",
                    "photo-url": "/images/default_user_image.png",
                    "athlete-interested": false,
                    "team-coach-recommended": false,
                    "match-percentage": null,
                    "last-activity": {
                        "last-profile-view-date": null,
                        "coach-first-name": "Coach",
                        "coach-last-name": "Test36033",
                        "coach-position": "",
                        "coach-recent-action": "follow",
                        "last-activity-date": "2015-06-01T00:00:00.000-05:00"
                    },
                    "activity-summary": {
                        "follows-count": 5,
                        "profile-views-count": 0,
                        "athlete-sent-emails-count": 0,
                        "athlete-received-emails-count": 0
                    }
                }
            ]
        }
    },
    "links": {
        "self": "/api/team_edition/organizations/1/colleges/16038"
    }
}
```


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

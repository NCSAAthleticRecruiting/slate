## Get a College

> Sample Successful Request

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/colleges/16038 \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{\n  "data": {\n    "type": "organizations",\n    "attributes": {\n      "name": "Test Club Uno",\n      "zip-code": "60642",\n      "address": "234 Maple Lane",\n      "city": "Chicago",\n      "state": "IL",\n      "email": "clubtest@ncsasports.tst",\n      "phone": "1234567899",\n      "website": "http://www.example.com",\n      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"\n    }\n  }\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/colleges/16038")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request.body = "{\n  \"data\": {\n    \"type\": \"organizations\",\n    \"attributes\": {\n      \"name\": \"Test Club Uno\",\n      \"zip-code\": \"60642\",\n      \"address\": \"234 Maple Lane\",\n      \"city\": \"Chicago\",\n      \"state\": \"IL\",\n      \"email\": \"clubtest@ncsasports.tst\",\n      \"phone\": \"1234567899\",\n      \"website\": \"http://www.example.com\",\n      \"logo-url\": \"//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg\"\n    }\n  }\n}"

response = http.request(request)
puts response.read_body
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "16038",
    "type": "colleges",
    "attributes": {
      "name": "NCSA",
      "city": "Fairfax",
      "state": "VA",
      "division": "NCAA I-A",
      "website": "",
      "type": "NONE",
      "private-or-public": "PRIVATE",
      "location-type": "URBAN",
      "academic-strength": 2,
      "tuition-instate": "28466.0",
      "tuition-outofstate": "38466.0",
      "enrollment": 2472,
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
          "name": "Coach Test29541",
          "position": "Head",
          "phone-number": "555-123-4568",
          "email": "coach29541@example.tst"
        }
      ],
      "activity": [
        {
          "id": "7",
          "team-name": "18 Elite",
          "first-name": "Chris",
          "last-name": "Heineken",
          "email": "chris.hein@ncsasports.tst",
          "ncsa-email": "chris.hein1@test.org",
          "position": "Outside Hitter",
          "grad-year": "2018",
          "photo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18132clid.jpg",
          "athlete-interested": false,
          "team-coach-recommended": true,
          "match-percentage": null,
          "last-activity": {
            "last-profile-view-date": null,
            "coach-first-name": null,
            "coach-last-name": null,
            "coach-position": null,
            "coach-recent-action": null,
            "last-activity-date": null
          },
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 0,
            "athlete-sent-emails-count": 0,
            "athlete-received-emails-count": 8
          }
        },
        {
          "id": "6",
          "team-name": "18 Elite",
          "first-name": "Georgina",
          "last-name": "Buchner-Wilson",
          "email": "georgie@ncsasports.tst",
          "ncsa-email": "george.buchner@test.org",
          "position": "Kicker",
          "grad-year": "2018",
          "photo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/573275clid.jpg",
          "athlete-interested": true,
          "team-coach-recommended": true,
          "match-percentage": 35,
          "last-activity": {
            "last-profile-view-date": "2017-01-04T13:00:57.630-06:00",
            "coach-first-name": "Coach",
            "coach-last-name": "Test15876",
            "coach-position": "RC",
            "coach-recent-action": "follow",
            "last-activity-date": "2017-01-04T13:01:08.510-06:00"
          },
          "activity-summary": {
            "follows-count": 1,
            "profile-views-count": 50,
            "athlete-sent-emails-count": 0,
            "athlete-received-emails-count": 5
          }
        },
        {
          "id": "5",
          "team-name": "18 Elite",
          "first-name": "GdillonMurphy",
          "last-name": "Murphy",
          "email": "gdillonmurphy@ncsa.tst",
          "ncsa-email": "gdillonmurphy.murphy@test.tst",
          "position": "Opposite",
          "grad-year": "2015",
          "photo-url": "/images/default_user_image.png",
          "athlete-interested": false,
          "team-coach-recommended": true,
          "match-percentage": null,
          "last-activity": {
            "last-profile-view-date": "2016-10-11T11:08:11.107-05:00",
            "coach-first-name": "Coach",
            "coach-last-name": "Test15876",
            "coach-position": "RC",
            "coach-recent-action": "view",
            "last-activity-date": "2016-10-11T11:08:11.107-05:00"
          },
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 1,
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

GET for retrieving a college resource

### HTTP Request

`GET /api/team_edition/organizations/[:organization_id]/colleges/[:college_id]`

### Headers

**Content-Type** | application/vnd.api+json

**Session-Token** | eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9

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
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/6/activity")

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
  "data": {
    "id": "6",
    "type": "athlete-activities",
    "attributes": {
      "last-login": "2017-02-24T12:53:31.473-06:00",
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
          "weeks-ago": 0,
          "follow-count": 0,
          "view-count": 0,
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
          "weeks-ago": 2,
          "follow-count": 0,
          "view-count": 3,
          "message-received-count": 4
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
          "weeks-ago": 4,
          "follow-count": 1,
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
          "weeks-ago": 8,
          "follow-count": 0,
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
          "weeks-ago": 10,
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
          "last-activity-date": "2017-02-24T13:30:18.000-06:00",
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
          "last-activity-date": "2017-02-24T13:30:03.000-06:00",
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
          "last-activity-date": "2017-02-24T13:30:20.000-06:00",
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
        },
        {
          "college-name": "Alabama A&M University",
          "college-id": "13859",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Normal",
          "college-state": "AL",
          "college-state-name": "ALABAMA",
          "match-percentage": 8,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13859college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 1,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15606",
          "college-name": "University of Colorado - Boulder",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Boulder",
          "college-state": "CO",
          "college-state-name": "COLORADO",
          "match-percentage": 64,
          "last-activity-date": "2017-02-09T14:43:40.000-06:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15606college.jpg",
          "ncsa-match": false,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 2,
            "profile-views-count": 23,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13861",
          "college-name": "Alabama State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Montgomery",
          "college-state": "AL",
          "college-state-name": "ALABAMA",
          "match-percentage": 14,
          "last-activity-date": "2017-02-06T16:54:44.533-06:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13861college.jpg",
          "ncsa-match": false,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 3,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15566",
          "college-name": "United States Military Academy at West Point",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "West  Point",
          "college-state": "NY",
          "college-state-name": "NEW YORK",
          "match-percentage": 65,
          "last-activity-date": "2017-02-06T16:30:02.000-06:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15566college.jpg",
          "ncsa-match": false,
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
          "college-id": "15077",
          "college-name": "Ohio State University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Columbus",
          "college-state": "OH",
          "college-state-name": "OHIO",
          "match-percentage": 43,
          "last-activity-date": "2016-10-07T11:30:07.000-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15077college.jpg",
          "ncsa-match": false,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 12,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15449",
          "college-name": "Stanford University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Stanford",
          "college-state": "CA",
          "college-state-name": "CALIFORNIA",
          "match-percentage": 81,
          "last-activity-date": "2016-08-23T15:45:07.000-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15449college.jpg",
          "ncsa-match": true,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 3,
            "profile-views-count": 8,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15516",
          "college-name": "Texas Christian University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Fort Worth",
          "college-state": "TX",
          "college-state-name": "TEXAS",
          "match-percentage": 8,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15516college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15744",
          "college-name": "University of Utah",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Salt Lake City",
          "college-state": "UT",
          "college-state-name": "UTAH",
          "match-percentage": 55,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15864college.jpg",
          "ncsa-match": false,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 10,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15629",
          "college-name": "University of Indianapolis",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Indianapolis",
          "college-state": "IN",
          "college-state-name": "INDIANA",
          "match-percentage": 26,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18641college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14447",
          "college-name": "Florida State University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Tallahassee",
          "college-state": "FL",
          "college-state-name": "FLORIDA",
          "match-percentage": 52,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15680college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14341",
          "college-name": "Dickinson State University",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Dickinson",
          "college-state": "ND",
          "college-state-name": "NORTH DAKOTA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14334college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14639",
          "college-name": "Ithaca College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Ithaca",
          "college-state": "NY",
          "college-state-name": "NEW YORK",
          "match-percentage": 3,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/11626college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15652",
          "college-name": "University of Memphis",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Memphis",
          "college-state": "TN",
          "college-state-name": "TENNESSEE",
          "match-percentage": 11,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15652college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15057",
          "college-name": "Northwood University - Cedar Hill",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Cedar Hill",
          "college-state": "TX",
          "college-state-name": "TEXAS",
          "match-percentage": 3,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17598college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14092",
          "college-name": "Carroll College",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Helena",
          "college-state": "MT",
          "college-state-name": "MONTANA",
          "match-percentage": 2,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13926college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 6,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14433",
          "college-name": "Ferrum College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Ferrum",
          "college-state": "VA",
          "college-state-name": "VIRGINIA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/07901college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14579",
          "college-name": "Hobart & William Smith Colleges",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Geneva",
          "college-state": "NY",
          "college-state-name": "NEW YORK",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14579college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 8,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13912",
          "college-name": "Appalachian State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Boone",
          "college-state": "NC",
          "college-state-name": "NORTH CAROLINA",
          "match-percentage": 68,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13912college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15904",
          "college-name": "Winona State University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Winona",
          "college-state": "MN",
          "college-state-name": "MINNESOTA",
          "match-percentage": 21,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15904college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14851",
          "college-name": "McNeese State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Lake Charles",
          "college-state": "LA",
          "college-state-name": "LOUISIANA",
          "match-percentage": 61,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17786college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15841",
          "college-name": "West Chester University of Pennsylvania",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "West Chester",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 19,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17665college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 6,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14925",
          "college-name": "Monmouth University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "West Long Branch",
          "college-state": "NJ",
          "college-state-name": "NEW JERSEY",
          "match-percentage": 39,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14656college.jpg",
          "ncsa-match": false,
          "athlete-interested": true,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13921",
          "college-name": "Arkansas Tech University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Russellville",
          "college-state": "AR",
          "college-state-name": "ARKANSAS",
          "match-percentage": 29,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13921college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 6,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14917",
          "college-name": "Missouri Valley College",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Marshall",
          "college-state": "MO",
          "college-state-name": "MISSOURI",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18069college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15661",
          "college-name": "University of Missouri",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Columbia",
          "college-state": "MO",
          "college-state-name": "MISSOURI",
          "match-percentage": 39,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15661college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14619",
          "college-name": "Indiana University of Pennsylvania",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Indiana",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 12,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14619college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14136",
          "college-name": "University of Central Missouri",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Warrensburg",
          "college-state": "MO",
          "college-state-name": "MISSOURI",
          "match-percentage": 25,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14136college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15656",
          "college-name": "University of Minnesota - Crookston",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Crookston",
          "college-state": "MN",
          "college-state-name": "MINNESOTA",
          "match-percentage": 5,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/06844college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15610",
          "college-name": "University of Dayton",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Dayton",
          "college-state": "OH",
          "college-state-name": "OHIO",
          "match-percentage": 23,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18032college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14036",
          "college-name": "Brown University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Providence",
          "college-state": "RI",
          "college-state-name": "RHODE ISLAND",
          "match-percentage": 26,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14036college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 10,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14485",
          "college-name": "Geneva College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Beaver Falls",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18370college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14004",
          "college-name": "Bloomsburg University of Pennsylvania",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Bloomsburg",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 14,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17772college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14479",
          "college-name": "Gardner-Webb University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Boiling Springs",
          "college-state": "NC",
          "college-state-name": "NORTH CAROLINA",
          "match-percentage": 55,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/20855college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15092",
          "college-name": "Olivet Nazarene University",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Bourbonnais",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": 2,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/16501college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15335",
          "college-name": "South Carolina State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Orangeburg",
          "college-state": "SC",
          "college-state-name": "SOUTH CAROLINA",
          "match-percentage": 25,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/no_school.png",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14931",
          "college-name": "Montana Tech of the University of Montana",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Butte",
          "college-state": "MT",
          "college-state-name": "MONTANA",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18084college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14596",
          "college-name": "Humboldt State University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Arcata",
          "college-state": "CA",
          "college-state-name": "CALIFORNIA",
          "match-percentage": 30,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/20957college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14610",
          "college-name": "Illinois Wesleyan University",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Bloomington",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": 5,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12197college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14490",
          "college-name": "Georgetown College",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Georgetown",
          "college-state": "KY",
          "college-state-name": "KENTUCKY",
          "match-percentage": 3,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13092college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 8,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14822",
          "college-name": "Marist College",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Poughkeepsie",
          "college-state": "NY",
          "college-state-name": "NEW YORK",
          "match-percentage": 21,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14822college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15329",
          "college-name": "Slippery Rock University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Slippery Rock",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 15,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/21932college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14736",
          "college-name": "Lebanon Valley College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Annville",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12325college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15260",
          "college-name": "Sacred Heart University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Fairfield",
          "college-state": "CT",
          "college-state-name": "CONNECTICUT",
          "match-percentage": 13,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18058college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14708",
          "college-name": "Lake Forest College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Lake Forest",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18573college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14806",
          "college-name": "Maine Maritime Academy",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Castine",
          "college-state": "ME",
          "college-state-name": "MAINE",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/no_school.png",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13961",
          "college-name": "Bates College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Lewiston",
          "college-state": "ME",
          "college-state-name": "MAINE",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13961college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13973",
          "college-name": "Benedictine College",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Atchison",
          "college-state": "KS",
          "college-state-name": "KANSAS",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13973college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15630",
          "college-name": "University of Iowa",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Iowa City",
          "college-state": "IA",
          "college-state-name": "IOWA",
          "match-percentage": 65,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15630college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 1,
            "profile-views-count": 174,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15106",
          "college-name": "Ouachita Baptist University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Arkadelphia",
          "college-state": "AR",
          "college-state-name": "ARKANSAS",
          "match-percentage": 29,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12989college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14943",
          "college-name": "Morehead State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Morehead",
          "college-state": "KY",
          "college-state-name": "KENTUCKY",
          "match-percentage": 35,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14790college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13901",
          "college-name": "Anderson University - Indiana",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Anderson",
          "college-state": "IN",
          "college-state-name": "INDIANA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13901college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13987",
          "college-name": "Bethel Seminary - St. Paul",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Saint Paul",
          "college-state": "MN",
          "college-state-name": "MINNESOTA",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17645college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 6,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14273",
          "college-name": "Cornell University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Ithaca",
          "college-state": "NY",
          "college-state-name": "NEW YORK",
          "match-percentage": 38,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/21364college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15916",
          "college-name": "Yale University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "New Haven",
          "college-state": "CT",
          "college-state-name": "CONNECTICUT",
          "match-percentage": 56,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15916college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15816",
          "college-name": "Washburn University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Topeka",
          "college-state": "KS",
          "college-state-name": "KANSAS",
          "match-percentage": 17,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/19028college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14388",
          "college-name": "Edinboro University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Edinboro",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 14,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/20618college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13947",
          "college-name": "Baldwin Wallace University",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Berea",
          "college-state": "OH",
          "college-state-name": "OHIO",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13678college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15567",
          "college-name": "United States Naval Academy",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Annapolis",
          "college-state": "MD",
          "college-state-name": "MARYLAND",
          "match-percentage": 29,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15567college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 10,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14860",
          "college-name": "Mercyhurst University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Erie",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 22,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/07221college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14027",
          "college-name": "Bridgewater State University",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Bridgewater",
          "college-state": "MA",
          "college-state-name": "MASSACHUSETTS",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14027college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15407",
          "college-name": "St. Cloud State University",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Saint Cloud",
          "college-state": "MN",
          "college-state-name": "MINNESOTA",
          "match-percentage": 33,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/20261college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14946",
          "college-name": "Morningside College",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Sioux City",
          "college-state": "IA",
          "college-state-name": "IOWA",
          "match-percentage": 4,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14946college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14883",
          "college-name": "Middlebury College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Middlebury",
          "college-state": "VT",
          "college-state-name": "VERMONT",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/11124college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14697",
          "college-name": "Knox College",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Galesburg",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": 2,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/05294college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13964",
          "college-name": "Belhaven University",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Jackson",
          "college-state": "MS",
          "college-state-name": "MISSISSIPPI",
          "match-percentage": 1,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/17322college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14944",
          "college-name": "Morehouse College",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Atlanta",
          "college-state": "GA",
          "college-state-name": "GEORGIA",
          "match-percentage": 33,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/10300college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14228",
          "college-name": "College of the Holy Cross",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Worcester",
          "college-state": "MA",
          "college-state-name": "MASSACHUSETTS",
          "match-percentage": 28,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14228college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14374",
          "college-name": "Eastern Illinois University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Charleston",
          "college-state": "IL",
          "college-state-name": "ILLINOIS",
          "match-percentage": 67,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14374college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 1,
            "profile-views-count": 6,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14234",
          "college-name": "College of William & Mary",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Williamsburg",
          "college-state": "VA",
          "college-state-name": "VIRGINIA",
          "match-percentage": 39,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14450college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15316",
          "college-name": "Shippensburg University of Pennsylvania",
          "division-name": "NCAA II",
          "division-display-order": 40,
          "college-city": "Shippensburg",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 5,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18267college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14932",
          "college-name": "Montclair State University",
          "division-name": "NCAA III",
          "division-display-order": 50,
          "college-city": "Montclair",
          "college-state": "NJ",
          "college-state-name": "NEW JERSEY",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14673college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14028",
          "college-name": "Brigham Young University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Provo",
          "college-state": "UT",
          "college-state-name": "UTAH",
          "match-percentage": 46,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14028college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "13942",
          "college-name": "Azusa Pacific University",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Azusa",
          "college-state": "CA",
          "college-state-name": "CALIFORNIA",
          "match-percentage": 3,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/20903college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 4,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15453",
          "college-name": "Sterling College - Kansas",
          "division-name": "NAIA",
          "division-display-order": 60,
          "college-city": "Sterling",
          "college-state": "KS",
          "college-state-name": "KANSAS",
          "match-percentage": 0,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15453college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14643",
          "college-name": "Jacksonville State University",
          "division-name": "NCAA I-AA",
          "division-display-order": 20,
          "college-city": "Jacksonville",
          "college-state": "AL",
          "college-state-name": "ALABAMA",
          "match-percentage": 44,
          "last-activity-date": "2016-07-15T15:23:41.563-05:00",
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/19434college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": true,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 2,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15605",
          "college-name": "University of Cincinnati",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Cincinnati",
          "college-state": "OH",
          "college-state-name": "OHIO",
          "match-percentage": 38,
          "last-activity-date": null,
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/10905college.jpg",
          "ncsa-match": false,
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
          "college-id": "15658",
          "college-name": "University of Minnesota - Twin Cities",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Minneapolis",
          "college-state": "MN",
          "college-state-name": "MINNESOTA",
          "match-percentage": 58,
          "last-activity-date": null,
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15658college.jpg",
          "ncsa-match": false,
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
          "college-id": "15693",
          "college-name": "University of Oregon",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Eugene",
          "college-state": "OR",
          "college-state-name": "OREGON",
          "match-percentage": 41,
          "last-activity-date": null,
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15693college.jpg",
          "ncsa-match": false,
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
          "college-id": "15636",
          "college-name": "University of Louisville",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Louisville",
          "college-state": "KY",
          "college-state-name": "KENTUCKY",
          "match-percentage": 50,
          "last-activity-date": null,
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/16168college.jpg",
          "ncsa-match": false,
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
          "college-id": "15646",
          "college-name": "University of Maryland - College Park",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "College Park",
          "college-state": "MD",
          "college-state-name": "MARYLAND",
          "match-percentage": 44,
          "last-activity-date": null,
          "team-coach-recommended": false,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15646college.jpg",
          "ncsa-match": false,
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
          "college-id": "14854",
          "college-name": "Mendocino College",
          "division-name": "JC",
          "division-display-order": 70,
          "college-city": "Ukiah",
          "college-state": "CA",
          "college-state-name": "CALIFORNIA",
          "match-percentage": 12,
          "last-activity-date": null,
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14854college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": false,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 0,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "15504",
          "college-name": "Temple University",
          "division-name": "NCAA I-A",
          "division-display-order": 10,
          "college-city": "Philadelphia",
          "college-state": "PA",
          "college-state-name": "PENNSYLVANIA",
          "match-percentage": 23,
          "last-activity-date": null,
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18548college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": false,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 0,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        },
        {
          "college-id": "14429",
          "college-name": "Feather River College",
          "division-name": "JC",
          "division-display-order": 70,
          "college-city": "Quincy",
          "college-state": "CA",
          "college-state-name": "CALIFORNIA",
          "match-percentage": 3,
          "last-activity-date": null,
          "team-coach-recommended": true,
          "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14429college.jpg",
          "ncsa-match": false,
          "athlete-interested": false,
          "college-activity": false,
          "activity-summary": {
            "follows-count": 0,
            "profile-views-count": 0,
            "athlete-received-emails-count": 0,
            "athlete-sent-emails-count": 0
          }
        }
      ],
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
    "self": "/api/team_edition/athletes/6/activity"
  }
}

```



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

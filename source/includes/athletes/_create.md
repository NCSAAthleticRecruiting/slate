# Create an athlete


`POST /api/team_edition/organizations/[:organization_id]/athletes`


**Sample Headers**
* `Content-Type`: `application/vnd.api+json`
* `Session-Token`: `eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9`


* Sample Request Body

```json
{
  "data": {
    "type": "athletes",
    "attributes": {
      "first_name": "Peter",
      "last_name": "Buckets",
      "email": "petebuckets@example.com",
      "phone": "5036805403",
      "zip_code": "60613",
      "graduation_year": "2021",
      "event_id": 1
    },
    "relationships": {
      "team": {
        "data": {
          "type": "teams",
          "id": "4"
        }
      }
    }
  }
}
```

<br>

### Sample Successful Requests

**cURL**

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
  --data-binary '{"data":{"type":"athletes","attributes":{"first_name":"Peter","last_name":"Buckets","email":"petebuckets@example.com","phone":"5036805403","zip_code":"60613","graduation_year":"2021","event_id":1},"relationships":{"team":{"data":{"type":"teams","id":"4"}}}}}'
```


#### 2. Ruby Net::HTTP

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/athletes")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'
request.body =  "{\"data\":{\"type\":\"athletes\",\"attributes\":{\"first_name\":\"Peter\",\"last_name\":\"Buckets\",\"email\":\"petebuckets@example.com\",\"phone\":\"5036805403\",\"zip_code\":\"60613\",\"graduation_year\":\"2021\",\"event_id\":1},\"relationships\":{\"team\":{\"data\":{\"type\":\"teams\",\"id\":\"4\"}}}}}"

response = http.request(request)
puts response.read_body
```

<br>
<br>

## _Sample Successful Response_

```json
{
  "data": {
    "id": "45",
    "type": "athletes",
    "attributes": {
      "organization-id": 1,
      "client-id": 776050,
      "primary-team-name": "Men's Traveling Elite",
      "sport-id": 17695,
      "profile": {
        "first-name": "Peter",
        "last-name": "Buckets",
        "email": "petebuckets@example.com",
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
      "self": "/api/team_edition/athletes/45"
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/45"
  }
}
```

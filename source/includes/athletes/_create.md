# CREATE AN ATHLETE

**POST `/api/team_edition/organizations/:organization_id/athletes`**

This endpoint creates a team edition athlete.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |

**Required Data**

* attributes
  - `first_name`
  - `last_name`
  - `email`
  - `phone`
  - `zip_code`
  - `graduation_year`
* type (`athletes`)
* relationships
  - `team`

**Sample Request Payload**

```json
{
  "data": {
    "type": "athletes",
    "attributes": {
      "first_name": "Renata ",
      "last_name": "Stauder",
      "email": "rstauder@example.com",
      "phone": "5556805400",
      "zip_code": "56803",
      "graduation_year": "2020",
      "event_id": 1
    },
    "relationships": {
      "team": {
        "data": {
          "type": "teams",
          "id": "3"
        }
      }
    }
  }
}
```

**Code Examples**

_cURL_

```shell
curl --request POST \
  http://qa.ncsasports.org/api/team_edition/organizations/1/athletes \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9' \
  --data-binary '{"data":{"type":"athletes","attributes":{"first_name":"Renata ","last_name":"Stauder","email":"cjo.ncsa@gmail.com","phone":"5556805400","zip_code":"56803","graduation_year":"2020","event_id":1},"relationships":{"team":{"data":{"type":"teams","id":"3"}}}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/athletes/")
options = {"data":{"type":"athletes","attributes":{"first_name":"Renata ","last_name":"Stauder","email":"cjo.ncsa@gmail.com","phone":"5556805400","zip_code":"56803","graduation_year":"2020","event_id":1},"relationships":{"team":{"data":{"type":"teams","id":"3"}}}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

```json
/* 201 Created */
{
  "data": {
    "id": "48",
    "type": "athletes",
    "attributes": {
      "organization-id": 1,
      "client-id": null,
      "primary-team-name": "Women's Traveling Elite",
      "sport-id": 17696,
      "profile": {
        "first-name": "Renata ",
        "last-name": "Stauder",
        "email": "cjo.ncsa@gmail.com",
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
      "ncsa-profile-url": null,
      "deleted": false
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
      "self": "/api/team_edition/athletes/48"
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/48"
  }
}

```



## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

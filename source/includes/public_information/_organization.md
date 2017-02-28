# GET PUBLICLY VISIBLE INFORMATION FOR AN ORGANIZATION

**GET `/api/team_edition/public/organizations/:organization_id`**

This endpoint retrieves the information for an orgainzation that can be publicly visible.


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
  --url http:/qa.ncsasports.org/api/team_edition/public/organizations/1 \
  --header 'content-type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```

_Ruby Net:Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http:/qa.ncsasports.org/api/team_edition/public/organizations/1")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request['content-type'] = 'application/vnd.api+json'
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```

## Responses

**Sample Successful Response**

```json
{
  "data": {
    "id": "1",
    "type": "organizations",
    "attributes": {
      "name": "Spree Volleyball",
      "zip-code": "56906",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "org@example.com",
      "phone": "3122234567",
      "website": "http://www.example.com",
      "logo-url": "/images/default_organization_image.png"
    },
    "relationships": {
      "sports": {
        "data": [
          {
            "id": "1",
            "type": "organization-sports"
          },
          {
            "id": "2",
            "type": "organization-sports"
          }
        ]
      },
      "teams": {
        "data": [
          {
            "id": "1",
            "type": "teams"
          },
          {
            "id": "2",
            "type": "teams"
          },
          {
            "id": "3",
            "type": "teams"
          },
          {
            "id": "4",
            "type": "teams"
          }
        ]
      }
    },
    "links": {
      "self": "/api/team_edition/organizations/1"
    }
  },
  "included": [
    {
      "id": "1",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Women's Volleyball",
        "sport-id": 17696
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
        "self": "/api/team_edition/organizations/1/organization_sports"
      }
    },
    {
      "id": "2",
      "type": "organization-sports",
      "attributes": {
        "sport-name": "Men's Volleyball",
        "sport-id": 17695
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
        "self": "/api/team_edition/organizations/2/organization_sports"
      }
    },
    {
      "id": "1",
      "type": "teams",
      "attributes": {
        "name": "18 Elite",
        "sport": "Women's Volleyball",
        "sport-id": 17696,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "1",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/1"
      }
    },
    {
      "id": "2",
      "type": "teams",
      "attributes": {
        "name": "16 Elite",
        "sport": "Men's Volleyball",
        "sport-id": 17695,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "2",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/2"
      }
    },
    {
      "id": "3",
      "type": "teams",
      "attributes": {
        "name": "Women's Traveling Elite",
        "sport": "Women's Volleyball",
        "sport-id": 17696,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "1",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/3"
      }
    },
    {
      "id": "4",
      "type": "teams",
      "attributes": {
        "name": "Men's Traveling Elite",
        "sport": "Men's Volleyball",
        "sport-id": 17695,
        "active": true,
        "deleted": false
      },
      "relationships": {
        "organization-sport": {
          "data": {
            "id": "2",
            "type": "organization-sports"
          }
        }
      },
      "links": {
        "self": "/api/team_edition/teams/4"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1"
  }
}
```




## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

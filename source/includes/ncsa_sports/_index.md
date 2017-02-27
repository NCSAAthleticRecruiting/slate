# GET ALL SPORTS

**GET `/api/team_edition/ncsa_sports/`**

This endpoint shows all of the sports in team edition.

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
  "http:/qa.ncsasports.org/api/team_edition/ncsa_sports/" \
  --header 'content-type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \

```

<br>

_Ruby Net::HTTP_

```ruby
require 'uri'
require 'net/http'

url = URI("http:/qa.ncsasports.org/api/team_edition/ncsa_sports/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request['content-type'] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```




### Sample Response

```json
{
  "data": [
    {
      "id": "17633",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17633,
        "name": "Football"
      }
    },
    {
      "id": "17634",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17634,
        "name": "Softball"
      }
    },
    {
      "id": "17635",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17635,
        "name": "Wrestling"
      }
    },
    {
      "id": "17638",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17638,
        "name": "Men's Basketball"
      }
    },
    {
      "id": "17639",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17639,
        "name": "Women's Basketball"
      }
    },
    {
      "id": "17644",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17644,
        "name": "Men's Rowing"
      }
    },
    {
      "id": "17645",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17645,
        "name": "Women's Rowing"
      }
    },
    {
      "id": "17652",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17652,
        "name": "Men's Diving"
      }
    },
    {
      "id": "17653",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17653,
        "name": "Women's Diving"
      }
    },
    {
      "id": "17659",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17659,
        "name": "Men's Golf"
      }
    },
    {
      "id": "17660",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17660,
        "name": "Women's Golf"
      }
    },
    {
      "id": "17665",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17665,
        "name": "Men's Ice Hockey"
      }
    },
    {
      "id": "17666",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17666,
        "name": "Women's Ice Hockey"
      }
    },
    {
      "id": "17683",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17683,
        "name": "Men's Soccer"
      }
    },
    {
      "id": "17684",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17684,
        "name": "Women's Soccer"
      }
    },
    {
      "id": "17687",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17687,
        "name": "Men's Swimming"
      }
    },
    {
      "id": "17688",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17688,
        "name": "Women's Swimming"
      }
    },
    {
      "id": "17689",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17689,
        "name": "Men's Tennis"
      }
    },
    {
      "id": "17690",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17690,
        "name": "Women's Tennis"
      }
    },
    {
      "id": "17691",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17691,
        "name": "Men's Track"
      }
    },
    {
      "id": "17692",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17692,
        "name": "Women's Track"
      }
    },
    {
      "id": "17695",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17695,
        "name": "Men's Volleyball"
      }
    },
    {
      "id": "17696",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17696,
        "name": "Women's Volleyball"
      }
    },
    {
      "id": "17701",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17701,
        "name": "Men's Water Polo"
      }
    },
    {
      "id": "17702",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17702,
        "name": "Women's Water Polo"
      }
    },
    {
      "id": "17706",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17706,
        "name": "Baseball"
      }
    },
    {
      "id": "17707",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17707,
        "name": "Men's Lacrosse"
      }
    },
    {
      "id": "17708",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17708,
        "name": "Women's Lacrosse"
      }
    },
    {
      "id": "17711",
      "type": "ncsa-sports",
      "attributes": {
        "sport-id": 17711,
        "name": "Field Hockey"
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/ncsa_sports"
  }
}
```


## Errrors/Statuses

See relevant spec files.

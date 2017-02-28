# GET COLLEGES

**GET `/api/team_edition/organizations/:organization_id/colleges`**
**GET `/api/team_edition/organizations/:organization_id/colleges?filter[query]=<SearchTerm>`**

This endpoint is responsible for getting all colleges or a all colleges matching a query.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Query String Parameters**

| Name               | Required? | Description         |
|--------------------|-----------|---------------------|
| `filter[query]`    | false     | search term         |


**cURL**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/colleges \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \

curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/colleges?filter%5Bquery%5D=portland \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
```


**Ruby Net::HTTP**

```ruby
require 'URI'
require 'net/http'

url = URI("http://localhost:3000/api/team_edition/organizations/1/colleges")
# Uncomment the below line if you want a search url instead
# url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/colleges?filter%5Bquery%5D=portland")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'

response = http.request(request)
puts response.read_body
```


## Responses

**Sample Successful Response**

url: `http://qa.ncsasports.org/api/team_edition/organizations/1/colleges?filter[query]=portland`

```json
/* 200 OK */
{
  "data": [
    {
      "id": "14972",
      "type": "colleges",
      "attributes": {
        "name": "Multnomah University",
        "city": "Portland",
        "state": "OR",
        "division": "NCAA III",
        "website": "http://www.multnomah.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "22760.0",
        "tuition-outofstate": "22760.0",
        "enrollment": 355,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14972college.jpg",
        "sport-ids": [
          17638,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14747",
      "type": "colleges",
      "attributes": {
        "name": "Lewis & Clark College",
        "city": "Portland",
        "state": "OR",
        "division": "NCAA III",
        "website": "http://www.lclark.edu/",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "45104.0",
        "tuition-outofstate": "45104.0",
        "enrollment": 2156,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12582college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17644,
          17645,
          17659,
          17660,
          17683,
          17684,
          17687,
          17688,
          17689,
          17690,
          17691,
          17692,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14261",
      "type": "colleges",
      "attributes": {
        "name": "Concordia University - Oregon",
        "city": "Portland",
        "state": "OR",
        "division": "NAIA",
        "website": "http://www.cu-portland.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "28510.0",
        "tuition-outofstate": "28510.0",
        "enrollment": 1075,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12711college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
          17691,
          17692,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15182",
      "type": "colleges",
      "attributes": {
        "name": "Portland State University",
        "city": "Portland",
        "state": "OR",
        "division": "NCAA I",
        "website": "http://www.pdx.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "8034.0",
        "tuition-outofstate": "24009.0",
        "enrollment": 14561,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/16093college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17660,
          17684,
          17689,
          17690,
          17691,
          17692,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15721",
      "type": "colleges",
      "attributes": {
        "name": "University of Southern Maine",
        "city": "Portland",
        "state": "ME",
        "division": "NCAA III",
        "website": "http://www.usm.maine.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "7796.0",
        "tuition-outofstate": "18508.0",
        "enrollment": 3985,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14798college.jpg",
        "sport-ids": [
          17634,
          17635,
          17638,
          17639,
          17659,
          17660,
          17665,
          17666,
          17683,
          17684,
          17689,
          17690,
          17691,
          17692,
          17696,
          17706,
          17707,
          17708,
          17711
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15812",
      "type": "colleges",
      "attributes": {
        "name": "Warner Pacific College",
        "city": "Portland",
        "state": "OR",
        "division": "NAIA",
        "website": "http://www.warnerpacific.edu/",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "21460.0",
        "tuition-outofstate": "21460.0",
        "enrollment": 522,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15812college.jpg",
        "sport-ids": [
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
          17691,
          17692,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15699",
      "type": "colleges",
      "attributes": {
        "name": "University of Portland",
        "city": "Portland",
        "state": "OR",
        "division": "NCAA I",
        "website": "http://www.up.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "42288.0",
        "tuition-outofstate": "42288.0",
        "enrollment": 3609,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15699college.png",
        "sport-ids": [
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
          17689,
          17690,
          17691,
          17692,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/colleges"
  }
}
```





## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

# Show All Colleges

**GET `/api/team_edition/organizations/1/colleges`** OR **GET `/api/team_edition/organizations/1/colleges?filter[query]=<SearchTerm>&page[number]=<PageNumber>`**

This endpoint is responsible for getting a paginated list of colleges matching the user-entered search terms.

### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Request Parameters

**Query String Parameters**

| Parameter           | Required? | Description         |
|:-------------------:|:---------:|:-------------------:|
| `organization_id`   | `true`    | query string param  |
| `filter[query]`     | `false`   | query string param  |
| `page[number]`      | `false`   | page no/pagination  |

### Request Examples

**cURL**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/organizations/1/colleges
  --header "session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
  --header "content-type: application/vnd.api+json"
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/organizations/1/colleges")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

### Sample Responses

**/api/team_edition/organizations/1/colleges**

```json
{
  "data": [
    {
      "id": "13935",
      "type": "colleges",
      "attributes": {
        "name": "Augustana College - Illinois",
        "city": "Rock Island",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.augustana.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "38466.0",
        "tuition-outofstate": "38466.0",
        "enrollment": 2472,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13021college.jpg",
        "sport-ids": [
          17633,
          17634,
          17635,
          17638,
          17639,
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
          17706,
          17707,
          17708
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "13937",
      "type": "colleges",
      "attributes": {
        "name": "Aurora University",
        "city": "Aurora",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://aurora.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 2,
        "tuition-instate": "22080.0",
        "tuition-outofstate": "22080.0",
        "enrollment": 2832,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13937college.jpg",
        "sport-ids": [
          17633,
          17634,
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
          17706,
          17707,
          17708
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "13974",
      "type": "colleges",
      "attributes": {
        "name": "Benedictine University",
        "city": "Lisle",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.ben.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 3,
        "tuition-instate": "27465.0",
        "tuition-outofstate": "27465.0",
        "enrollment": 3072,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13310college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
          17687,
          17688,
          17690,
          17691,
          17692,
          17696,
          17706,
          17707
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "13997",
      "type": "colleges",
      "attributes": {
        "name": "Black Hawk College",
        "city": "Moline",
        "state": "IL",
        "division": "JC",
        "website": "http://www.bhc.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "7500.0",
        "tuition-outofstate": "7650.0",
        "enrollment": 2346,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13997college.jpg",
        "sport-ids": [
          17638,
          17639,
          17691,
          17692,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14000",
      "type": "colleges",
      "attributes": {
        "name": "Blackburn College",
        "city": "Carlinville",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.blackburn.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "SUBURBAN",
        "academic-strength": 3,
        "tuition-instate": "20364.0",
        "tuition-outofstate": "20364.0",
        "enrollment": 554,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14000college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
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
      "id": "14017",
      "type": "colleges",
      "attributes": {
        "name": "Bradley University",
        "city": "Peoria",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.bradley.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "31480.0",
        "tuition-outofstate": "31480.0",
        "enrollment": 4370,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/11259college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17660,
          17665,
          17683,
          17689,
          17690,
          17692,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14088",
      "type": "colleges",
      "attributes": {
        "name": "Carl Sandburg College",
        "city": "Galesburg",
        "state": "IL",
        "division": "JC",
        "website": "http://www.sandburg.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "6014.0",
        "tuition-outofstate": "7078.0",
        "enrollment": 956,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14088college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17660,
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
      "id": "14157",
      "type": "colleges",
      "attributes": {
        "name": "Chicago State University",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.csu.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "9994.0",
        "tuition-outofstate": "16954.0",
        "enrollment": 2498,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14157college.jpg",
        "sport-ids": [
          17638,
          17639,
          17659,
          17660,
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
      "id": "14207",
      "type": "colleges",
      "attributes": {
        "name": "College of DuPage",
        "city": "Glen Ellyn",
        "state": "IL",
        "division": "JC",
        "website": "http://www.cod.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "10885.0",
        "tuition-outofstate": "12985.0",
        "enrollment": 10022,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/11816college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17652,
          17653,
          17659,
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
      "id": "14209",
      "type": "colleges",
      "attributes": {
        "name": "College of Lake County",
        "city": "Grayslake",
        "state": "IL",
        "division": "JC",
        "website": "http://WWW.CLCILLINOIS.EDU",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "8358.0",
        "tuition-outofstate": "11046.0",
        "enrollment": 4303,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14209college.jpg",
        "sport-ids": [
          17634,
          17635,
          17638,
          17639,
          17659,
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
    },
    {
      "id": "14255",
      "type": "colleges",
      "attributes": {
        "name": "Concordia University Chicago",
        "city": "River Forest",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.cuchicago.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 3,
        "tuition-instate": "29520.0",
        "tuition-outofstate": "29520.0",
        "enrollment": 1397,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15470college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
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
    },
    {
      "id": "14312",
      "type": "colleges",
      "attributes": {
        "name": "Danville Area Community College",
        "city": "Danville",
        "state": "IL",
        "division": "JC",
        "website": "http://www.dacc.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "6375.0",
        "tuition-outofstate": "6375.0",
        "enrollment": 1069,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/12700college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17683,
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
      "id": "14335",
      "type": "colleges",
      "attributes": {
        "name": "DePaul University",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.depaul.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "36361.0",
        "tuition-outofstate": "36361.0",
        "enrollment": 13643,
        "logo-url": null,
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17665,
          17683,
          17684,
          17689,
          17690,
          17691,
          17692,
          17696,
          17707
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14348",
      "type": "colleges",
      "attributes": {
        "name": "Dominican University",
        "city": "River Forest",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.dom.edu/",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 3,
        "tuition-instate": "30670.0",
        "tuition-outofstate": "30670.0",
        "enrollment": 1996,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18475college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
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
    },
    {
      "id": "14374",
      "type": "colleges",
      "attributes": {
        "name": "Eastern Illinois University",
        "city": "Charleston",
        "state": "IL",
        "division": "NCAA I",
        "website": "https://www.eiu.edu/",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "SUBURBAN",
        "academic-strength": 3,
        "tuition-instate": "11312.0",
        "tuition-outofstate": "13442.0",
        "enrollment": 6676,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14374college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17652,
          17653,
          17659,
          17660,
          17665,
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
      "id": "14395",
      "type": "colleges",
      "attributes": {
        "name": "Elgin Community College",
        "city": "Elgin",
        "state": "IL",
        "division": "JC",
        "website": "http://www.elgin.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "10439.0",
        "tuition-outofstate": "11959.0",
        "enrollment": 3564,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/10325college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
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
    },
    {
      "id": "14399",
      "type": "colleges",
      "attributes": {
        "name": "Elmhurst College",
        "city": "Elmhurst",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.elmhurst.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 2,
        "tuition-instate": "34450.0",
        "tuition-outofstate": "34450.0",
        "enrollment": 2699,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14399college.jpg",
        "sport-ids": [
          17633,
          17634,
          17635,
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
    },
    {
      "id": "14416",
      "type": "colleges",
      "attributes": {
        "name": "Eureka College",
        "city": "Eureka",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.eureka.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "SUBURBAN",
        "academic-strength": 3,
        "tuition-instate": "20510.0",
        "tuition-outofstate": "20510.0",
        "enrollment": 632,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/08061college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17652,
          17653,
          17659,
          17684,
          17687,
          17688,
          17689,
          17690,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14530",
      "type": "colleges",
      "attributes": {
        "name": "Greenville College",
        "city": "Greenville",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.greenville.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "SUBURBAN",
        "academic-strength": 3,
        "tuition-instate": "25088.0",
        "tuition-outofstate": "25088.0",
        "enrollment": 1031,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14530college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
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
    },
    {
      "id": "14567",
      "type": "colleges",
      "attributes": {
        "name": "Highland Community College - Illinois",
        "city": "Freeport",
        "state": "IL",
        "division": "JC",
        "website": "http://www.highland.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "SUBURBAN",
        "academic-strength": 4,
        "tuition-instate": "5199.0",
        "tuition-outofstate": "5415.0",
        "enrollment": 965,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14567college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14605",
      "type": "colleges",
      "attributes": {
        "name": "Illinois Central College",
        "city": "East Peoria",
        "state": "IL",
        "division": "JC",
        "website": "http://icc.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "8700.0",
        "tuition-outofstate": "10050.0",
        "enrollment": 3680,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18266college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
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
      "id": "14606",
      "type": "colleges",
      "attributes": {
        "name": "Illinois College",
        "city": "Jacksonville",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.ic.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "SUBURBAN",
        "academic-strength": 2,
        "tuition-instate": "31660.0",
        "tuition-outofstate": "31660.0",
        "enrollment": 952,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/05611college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17659,
          17660,
          17683,
          17684,
          17687,
          17688,
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
      "id": "14607",
      "type": "colleges",
      "attributes": {
        "name": "Illinois Institute of Technology",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://www.iit.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "43680.0",
        "tuition-outofstate": "43680.0",
        "enrollment": 2922,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/06140college.jpg",
        "sport-ids": [
          17638,
          17639,
          17652,
          17653,
          17683,
          17684,
          17687,
          17688,
          17691,
          17692,
          17696,
          17702,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14608",
      "type": "colleges",
      "attributes": {
        "name": "Illinois State University",
        "city": "Normal",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://illinoisstate.edu/",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 3,
        "tuition-instate": "13666.0",
        "tuition-outofstate": "21482.0",
        "enrollment": 17040,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/18662college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17653,
          17659,
          17660,
          17684,
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
      "id": "14609",
      "type": "colleges",
      "attributes": {
        "name": "Illinois Valley Community College",
        "city": "Oglesby",
        "state": "IL",
        "division": "JC",
        "website": "http://www.ivcc.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "10359.0",
        "tuition-outofstate": "11221.0",
        "enrollment": 1467,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14609college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17689,
          17690,
          17696,
          17706
        ],
        "coaches": null,
        "activity": null
      }
    }
  ],
  "links": {
    "self": "/api/team_edition/organizations/1/colleges?page%5Bnumber%5D=1",
    "first": "/api/team_edition/organizations/1/colleges?page%5Bnumber%5D=1",
    "last": "/api/team_edition/organizations/1/colleges?page%5Bnumber%5D=4",
    "prev": null,
    "next": "/api/team_edition/organizations/1/colleges?page%5Bnumber%5D=2"
  }
}
```


**/api/team_edition/organizations/1/colleges?filter[query]=chicago**

```json
{
  "data": [
    {
      "id": "14787",
      "type": "colleges",
      "attributes": {
        "name": "Loyola University Chicago",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.luc.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "40426.0",
        "tuition-outofstate": "40426.0",
        "enrollment": 9331,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/13305college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17660,
          17665,
          17683,
          17684,
          17691,
          17692,
          17695,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "14255",
      "type": "colleges",
      "attributes": {
        "name": "Concordia University Chicago",
        "city": "River Forest",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.cuchicago.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "",
        "academic-strength": 3,
        "tuition-instate": "29520.0",
        "tuition-outofstate": "29520.0",
        "enrollment": 1397,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15470college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
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
    },
    {
      "id": "15026",
      "type": "colleges",
      "attributes": {
        "name": "North Park University",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://www.northpark.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "25860.0",
        "tuition-outofstate": "25860.0",
        "enrollment": 1911,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15026college.jpg",
        "sport-ids": [
          17633,
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
      "id": "14938",
      "type": "colleges",
      "attributes": {
        "name": "Moody Bible Institute",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://www.moody.edu",
        "type": "CHRISTIAN",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "12284.0",
        "tuition-outofstate": "12284.0",
        "enrollment": 2498,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/no_school.png",
        "sport-ids": [
          17638,
          17639,
          17683,
          17695,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15448",
      "type": "colleges",
      "attributes": {
        "name": "Saint Xavier University",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://WWW.SXU.EDU",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "30920.0",
        "tuition-outofstate": "30920.0",
        "enrollment": 2557,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/21087college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
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
      "id": "15604",
      "type": "colleges",
      "attributes": {
        "name": "University of Chicago",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA III",
        "website": "http://WWW.UCHICAGO.EDU",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 1,
        "tuition-instate": "51351.0",
        "tuition-outofstate": "51351.0",
        "enrollment": 5674,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/09595college.jpg",
        "sport-ids": [
          17633,
          17634,
          17635,
          17638,
          17639,
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
      "id": "14157",
      "type": "colleges",
      "attributes": {
        "name": "Chicago State University",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.csu.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "9994.0",
        "tuition-outofstate": "16954.0",
        "enrollment": 2498,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/14157college.jpg",
        "sport-ids": [
          17638,
          17639,
          17659,
          17660,
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
      "id": "14335",
      "type": "colleges",
      "attributes": {
        "name": "DePaul University",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.depaul.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "36361.0",
        "tuition-outofstate": "36361.0",
        "enrollment": 13643,
        "logo-url": null,
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
          17665,
          17683,
          17684,
          17689,
          17690,
          17691,
          17692,
          17696,
          17707
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15235",
      "type": "colleges",
      "attributes": {
        "name": "Robert Morris University - Illinois",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://www.robertmorris.edu/",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "25200.0",
        "tuition-outofstate": "25200.0",
        "enrollment": 2666,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15235college.jpg",
        "sport-ids": [
          17633,
          17634,
          17638,
          17639,
          17659,
          17660,
          17665,
          17666,
          17683,
          17684,
          17688,
          17690,
          17692,
          17695,
          17696,
          17706,
          17708
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15186",
      "type": "colleges",
      "attributes": {
        "name": "Prairie State College",
        "city": "Chicago Heights",
        "state": "IL",
        "division": "JC",
        "website": "http://www.prairiestate.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "",
        "academic-strength": 4,
        "tuition-instate": "7800.0",
        "tuition-outofstate": "9240.0",
        "enrollment": 1774,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/19279college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17659,
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
      "id": "16485",
      "type": "colleges",
      "attributes": {
        "name": "Roosevelt University",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://www.roosevelt.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "27300.0",
        "tuition-outofstate": "27300.0",
        "enrollment": 2953,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/16485college.jpg",
        "sport-ids": [
          17638,
          17639,
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
      "id": "14680",
      "type": "colleges",
      "attributes": {
        "name": "Kendall College",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "www.kendall.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 4,
        "tuition-instate": "24246.0",
        "tuition-outofstate": "24246.0",
        "enrollment": 1068,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/no_school.png",
        "sport-ids": [
          17638,
          17639,
          17695,
          17696
        ],
        "coaches": null,
        "activity": null
      }
    },
    {
      "id": "15627",
      "type": "colleges",
      "attributes": {
        "name": "University of Illinois at Chicago",
        "city": "Chicago",
        "state": "IL",
        "division": "NCAA I",
        "website": "http://www.uic.edu",
        "type": "NONE",
        "private-or-public": "PUBLIC",
        "location-type": "URBAN",
        "academic-strength": 3,
        "tuition-instate": "13664.0",
        "tuition-outofstate": "26520.0",
        "enrollment": 15459,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/15627college.jpg",
        "sport-ids": [
          17634,
          17638,
          17639,
          17652,
          17653,
          17683,
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
      "id": "14607",
      "type": "colleges",
      "attributes": {
        "name": "Illinois Institute of Technology",
        "city": "Chicago",
        "state": "IL",
        "division": "NAIA",
        "website": "http://www.iit.edu",
        "type": "NONE",
        "private-or-public": "PRIVATE",
        "location-type": "URBAN",
        "academic-strength": 2,
        "tuition-instate": "43680.0",
        "tuition-outofstate": "43680.0",
        "enrollment": 2922,
        "logo-url": "http://recruit-match.ncsasports.org/fasttrack/clientimages/06140college.jpg",
        "sport-ids": [
          17638,
          17639,
          17652,
          17653,
          17683,
          17684,
          17687,
          17688,
          17691,
          17692,
          17696,
          17702,
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

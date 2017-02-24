# Show Preferences

**GET /api/team_edition/athletes/:athlete_id/preferences`**

This endpoint retrieves the athlete's preferences.


### Sample Request Headers

<aside class="notice">The session token is stored in a cookie named `team_rms_session`</aside>

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJhbG...  | `true`    |
| _Content-Type_    | application/vnd.api+json   | `true`    |


### Sample Request Parameters

| Parameter    | Required? | Description         |
|:------------:|:---------:|:-------------------:|
|`athlete_id`  | 120       | query string param  |


### Request Examples

**cURL**

```shell
curl --request GET \
  --url http://qa.ncsasports.org/api/team_edition/athletes/5/preferences \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
```

<br>

**Ruby Net::HTTP**

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/athletes/5/preferences")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
request["content-type"] = 'application/vnd.api+json'

response = http.request(request)
puts response.read_body
```

<br>

## _Sample Successful Response_

```json
{
  "data": {
    "id": "5",
    "type": "athlete-preferences",
    "attributes": {
      "athletic-selectivity": [],
      "academic-selectivity": [],
      "college-setting": [],
      "college-type": [],
      "major": [],
      "enrollment-min": null,
      "enrollment-max": null,
      "location": [],
      "id": 5
    }
  },
  "links": {
    "self": "/api/team_edition/athletes/5/preferences"
  },
  "relationships": {
    "athlete": {
      "data": {
        "id": 5,
        "type": "athletes"
      }
    }
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

## CREATE session

**POST `/api/team_edition/sign_in`**

This endpoint is responsible for the control flow once a user submits the login form. A new `Session` for the authenticated user is initialized when the request succeeded.

### Request Headers

| Header            | Value                      | Required? |
|-------------------|----------------------------|-----------|
| _Session-Token_   | eyJ0eXAiOiJKV1QiLCJ...     | `true`    |
| _Content-Type_    | `application/vnd.api+json` | `true`    |

### Request Body

| Parameter  | Required? | Description  |
|:----------:|:---------:|:------------:|
|`email`     | `true`    |              |
|`password`  | `true`    |              |
|`type`      | `true`    | "sessions"   |


## Sample Requests

**cURL**

```shell
curl --request POST \
  http://qa.ncsasports.org/api/team_edition/sign_in
  --header 'Content-Type: application/vnd.api+json' \
  --header 'Session-Token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9' \
  --data '{"data": {"type":"sessions","attributes":{"email":"mia@example.com","password":"password"}}}'
```

<br>

**Ruby Net::Http**

```ruby
require 'uri'
require 'net/http'

http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)

request['content-type'] = 'application/vnd.api+json'
request['session-token'] = 'eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9'
options = {"data":{"type":"sessions","attributes":{"email":"mia@example.com","password":"password"}}}

request.body = options.to_json

response = http.request(request)
puts response.read_body
```

<br>

### Sample Response

<aside class="notice"><ul><li>Note that the self link is changed to the sign-in in page url in the AthleteIntegrations controller, and the `session-type` is set based on whether the user is a `Coach` or `PartnerAdmin`.</li></ul></aside>

```json
{
  "data": {
    "id": "1",
    "type": "sessions",
    "attributes": {
      "session-type": "partner_admin",
      "token": "eyJ0eXAiOiJKV1QiLCJhbGci"
    },
    "links": {
      "self": "/api/team_edition/sign_in"
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

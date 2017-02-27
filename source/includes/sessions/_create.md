# CREATE session

**POST `/api/team_edition/sign_in`**

This endpoint is responsible for the control flow once a user submits the login form. A new `Session` for the authenticated user is initialized when the request succeeded.

## Request

**Headers**

| Header            | `Type`/_Value_/Description        | Required?     |
|:------------------|:---------------------------------:|:-------------:|
| _Content-Type_    | `application/vnd.api+json`        | `true `       |

<br>

**Data Attributes**

| Attribute         | `Type`/_Value_/Description        | Required?     |
|:------------------|:----------------------------------|:--------------|
|`email`            | `String`                          | `true`        |
|`password`         | `String`                          | `true`        |
|`type`             | `String`/'sessions'               | `true`        |


**Sample Request Payload**

<aside class="notice>Must meet the JSON Api spec requirements for <a href="http://jsonapi.org/format/#crud-updating">updating a resource</a></aside>

```json
{
  "data": {
    "type": "sessions",
    "attributes": {
      "email": "john@example.com",
      "password": "password"
    }
  }
}
```

**Code Examples**
_cURL_

```shell
curl --request POST \
  --url "http://qa.ncsasports.org/api/team_edition/sign_in" \
  --header 'Content-Type: application/vnd.api+json' \
  --data '{"data":{"type":"sessions","attributes":{"email":"mia@example.com","password":"password"}}}'
```

<br>

_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

http = Net::HTTP.new(url.host, url.port)
request = Net::HTTP::Post.new(url)

request['content-type'] = 'application/vnd.api+json'
options = {"data":{"type":"sessions","attributes":{"email":"mia@example.com","password":"password"}}}

request.body = options.to_json

response = http.request(request)
puts response.read_body
```

<br>

## Response

<aside class="notice"><ul><li>Note that the self link is changed to the sign-in in page url in the AthleteIntegrations controller, and the `session-type` is set based on whether the user is a `Coach` or `PartnerAdmin`.</li></ul></aside>

```json

{
  "data": {
    "id": "2",
    "type": "sessions",
    "attributes": {
      "session-type": "coach",
      "token": "eyJ0eXAiOiJKV1QiLCJhbGci..."
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}
{
  "data": {
    "id": "1",
    "type": "sessions",
    "attributes": {
      "session-type": "partner_admin",
      "token": "eyJ0eXAiOiJKV1QiLCJhbGci..."
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}

```

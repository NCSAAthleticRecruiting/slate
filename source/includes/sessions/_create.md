# CREATE A SESSION

**POST `/api/team_edition/sign_in`**

This endpoint is responsible for the control flow once a user submits the login form. A new `Session` for the authenticated user is initialized when the request succeeded.


## Requests


**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |



**Required Attributes**

* `attributes['email']`
* `attributes['password']`


**Sample Request Payload**

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
  "http://qa.ncsasports.org/api/team_edition/sign_in" \
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

## Responses

<aside class="notice"><ul><li>Note that the self link is changed to the sign-in in page url in the AthleteIntegrations controller, and the `session-type` is set based on whether the user is a `Coach` or `PartnerAdmin`.</li></ul></aside>

```json
/* for a coach */
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
```

```json
/* for a partner admin */
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


## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

# UPDATE A PASSWORD FOR A USER

**PATCH `/api/team_edition/password_resets'`**

This endpoint handles updating a user's password once they've clicked the reset password button in the email they received (that gets sent via `POST /api/team_edition/password_resets/`) a user that has clicked through the reset password email.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |

**Required Attributes**

* `type`
* `attributes['password']`
* `attributes['password_reset_token']`

**Sample Request Payload**

```json
{
  "data": {
    "type": "coaches",
    "attributes": {
      "password": "password",
      "password_reset_token": "MBxT7VJQ8DfqNsdXXwuHcA"
    }
  }
}
 ```


**Code Samples**

_cURL_

```shell
curl --request PATCH \
  "http://qa.ncsasports.org/api/team_edition/password_resets" \
  --header 'content-type: application/vnd.api+json' \
  --data-binary '{"data":{"type":"coaches","attributes":{"password":"password","password_reset_token":"MBxT7VJQ8DfqNsdXXwuHcA"}}}'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/password_resets")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Patch.new(url)
request["content-type"] = 'application/vnd.api+json'
request.body = "{\"data\":{\"type\":\"coaches\",\"attributes\":{\"password\":\"password\",\"password_reset_token\":\"MBxT7VJQ8DfqNsdXXwuHcA\"}}}"

response = http.request(request)
puts response.read_body
```

## Responses

**Response Types**

| Status Code               | Description/Cause               |
|---------------------------|---------------------------------|
| 200 OK                    | Successfully updated password   |


**Response Data**

* `attributes['session-type']`
  * `coach` or `partner_admin`
* `attributes['token']`
  * the session token (aka the `team_rms_session` cookie)


**Sample Response Data**

```json
{
  "data": {
    "id": "72",
    "type": "sessions",
    "attributes": {
      "session-type": "coach",
      "token": "eyJ0eXAiOiJKV1QiLC..."
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}
```

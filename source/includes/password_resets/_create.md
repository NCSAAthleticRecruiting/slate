# CREATE A NEW PASSWORD/RESET PASSWORD FOR USER

**POST `/api/team_edition/password_resets`**

This endpoint handles resetting a user's password if the user has forgotten it and cannot log in.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |

**Required Attributes**

* `type`
* `attributes['email']`

**Sample Request Payload**

```json
{
  "data": {
    "type": "sessions",
    "attributes": {
      "email": "billmurray@example.com"
    }
  }
}
```

**Code Samples**

_cURL_

```shell
curl --request POST \
  "http://qa.ncsasports.org/api/team_edition/password_resets" \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data '{"data":{"type":"sessions","attributes":{"email":"billmurray@example.com"}}}'
```


_Ruby Net::Http_

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/password_resets")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::POST.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = "{"data":{"type":"sessions","attributes":{"email":"billmurray@example.com"}}}"

response = http.request(request)
puts response.read_body
```


## Responses

**Response Types**

| Status Code               | Description/Cause                                     |
|---------------------------|-------------------------------------------------------|
| 200 OK                    | Reset password email was successfully sent out        |


**Sample Successful Response**

```json
/* Emptiness */
{}
```

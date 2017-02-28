# CREATE A NEW PASSWORD/RESET PASSWORD FOR USER

**POST `/api/team_edition/password_resets`**

This endpoint handles resetting a user's password if the user has forgotten it and cannot log in.

## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |

**Required Data**

* `attributes`
  - `email`
* `type` ('sessions')

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
  --url http://qa.ncsasports.org/api/team_edition/password_resets \
  --header 'content-type: application/vnd.api+json' \
  --header 'session-token: eyJ0eXAiOiJKV1QiLCiJ9...' \
  --data-binary '{"data":{"type":"sessions","attributes":{"email":"billmurray@example.com"}}}' \
```


_Ruby Net::Http_

```ruby
require 'URI'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/password_resets")
options =  {"data":{"type":"sessions","attributes":{"email":"billmurray@example.com"}}}

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request["session-token"] = 'eyJ0eXAiOiJKV1QiLCiJ9...'
request.body = options.to_json

response = http.request(request)
puts response.read_body
```


## Responses


**Sample Successful Response**

```json
/* 200 OK */
{}
```



## Errrors/Statuses

See relevant spec files.

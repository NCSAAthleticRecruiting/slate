## Sign-In

> Sample Request Body:

```json
{
  "data": {
    "type": "sessions",
	  "attributes": {
	    "email": "lockjhart@ncsa.tst",
	    "password": "password"
	 }
  }
}
```

> Sample Successful Request:

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/sign_in")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request.body = "{\n  \"data\": {\n    \"type\": \"sessions\",\n\t  \"attributes\": {\n\t    \"email\": \"jlockhart@ncsasports.org\",\n\t    \"password\": \"password\"\n\t }\n  }\n}"

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/sign_in \
  --header 'content-type: application/vnd.api+json' \
  --data '{\n  "data": {\n    "type": "sessions",\n	  "attributes": {\n	    "email": "jlockhart@ncsasports.org",\n	    "password": "password"\n	 }\n  }\n}'
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "19",
    "type": "sessions",
    "attributes": {
      "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9"
    },
    "relationships": {
      "coach": {
        "data": {
          "id": "19",
          "type": "coaches"
        }
      },
      "organization": {
        "data": {
          "id": "9",
          "type": "organizations"
        }
      }
    },
    "links": {
      "self": "/api/team_edition/sign_in"
    }
  }
}
```
POST for team edition coach sign in

### HTTP Request

`POST /api/team_edition/sign_in`

### Headers

**Content-Type** | application/vnd.api+json

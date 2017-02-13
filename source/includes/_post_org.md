## Create an Organization

> Request Body:

```json
{
  "data": {
    "type": "organizations",
    "attributes": {
      "name": "New Club",
      "logo": {
      	"content_type": "image/png",
        "content": "iVBORw0KGgoAAAANSUhEUgAAAWsAAAGDCAYAAADtUTGXAAABfGlDQ1BJQ0MgUHJvZmlsZQAAKJFj
          YGAqSSwoyGFhYGDIzSspCnJ3UoiIjFJgv8PAzcDDIMRgxSCemFxc4BgQ4MOAE3y7xsAIoi/rgsxK
          8/x506a1fP4WNq+ZclYlOrj1gQF3SmpxMgMDIweQnZxSnJwLZOcA2TrJBUUlQPYMIFu3vKQAxD4B
          ZIsUAR0IZN8BsdMh7A8gdhKYzcQCVhMS5AxkSwDZAkkQtgaInQ5hW4DYyRmJKUC2B8guiBvAgNPD
          RcHcwFLXkYC7SQa5OaUwO0ChxZOaFxoMcgcQyzB4MLgwKDCYMxgwWDLoMjiWpFaUgBQ65xdUFmWm
          Z5QoOAJDNlXBOT+3oLQktUhHwTMvWU9HwcjA0ACkDhRnEKM/B4FNZxQ7jxDLX8jAYKnMwMDcgxBL
          msbAsH0PA4PEKYSYyjwGBn5rBoZt5woSixLhDmf8xkKIX5xmbARh8zgxMLDe+///sxoDA/skBoa/",
        "filename": "spec/support/image.png"
      },
      "zip_code": "60642",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "clubtest@ncsasports.tst",
      "phone": "1234567899",
      "website": "http://www.example.com",
      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"
    },
    "relationships": {
        "sport": {
        	"data": [{ "type": "sports", "id": "878" }]
        }
    }
  }
}
```

> Sample Successful Request:

```shell
curl --request POST \
  --url http://qa.ncsasports.org/api/team_edition/partners/1/organizations \
  --header 'content-type: application/vnd.api+json' \
  --data '{\n  "data": {\n    "type": "organizations",\n    "attributes": {\n      "name": "New Club",\n      "zip_code": "60642",\n      "address": "234 Maple Lane",\n      "city": "Chicago",\n      "state": "IL",\n      "email": "clubtest@ncsasports.tst",\n      "phone": "1234567899",\n      "website": "http://www.example.com",\n      "logo-url": "//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg"\n    }\n  }\n}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("http://qa.ncsasports.org/api/team_edition/partners/1/organizations")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/vnd.api+json'
request.body = "{\n  \"data\": {\n    \"type\": \"organizations\",\n    \"attributes\": {\n      \"name\": \"New Club\",\n      \"zip_code\": \"60642\",\n      \"address\": \"234 Maple Lane\",\n      \"city\": \"Chicago\",\n      \"state\": \"IL\",\n      \"email\": \"clubtest@ncsasports.tst\",\n      \"phone\": \"1234567899\",\n      \"website\": \"http://www.example.com\",\n      \"logo-url\": \"//s3.amazonaws.com/rms-rmfiles-staging/tmp/paperclip/org_4_profile.jpg\"\n    }\n  }\n}"

response = http.request(request)
puts response.read_body
```

> Sample Successful Response:

```json
{
  "data": {
    "id": "12",
    "type": "organizations",
    "attributes": {
      "name": "Test Club Uno",
      "zip-code": "60642",
      "address": "234 Maple Lane",
      "city": "Chicago",
      "state": "IL",
      "email": "clubtest@ncsasports.tst",
      "phone": "1234567899",
      "website": "http://www.example.com",
      "logo-url": "/images/default_organization_image.png",
      "sports": [
        "Women's Volleyball"
      ],
      "primary-contact-name": null
    },
    "links": {
      "self": "/api/team_edition/partners/1/organizations/12"
    }
  }
}
```

POST for creating an organization resource

### HTTP Request

`POST /api/team_edition/partners/1/organizations`

### Headers

**Content-Type** | application/vnd.api+json

# CREATE ATHLETES IN BULK

**POST `/api/team_edition/athletes/create_bulk`**

This endpoint handles creating multiple athletes at once via an uploaded CSV file.


## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |



**Required CSV Fields**

* `first_name`
* `last_name`
* `email`
* `primary_team`
* `graduation_year`
* `zip_code`
* `phone`

**Sample Parsed CSV Data**

```ruby
require 'smarter_csv'
athletes = SmarterCSV.process('/path/to/file.csv')

# athletes:
[
  {
    :first_name=>"Cristin",
    :last_name=>"O'Connor",
    :email=>"cristin@ncsasports.tst",
    :primary_team=>"Women's Traveling Elite",
    :graduation_year=>2019,
    :zip_code=>46556,
    :phone=>5556305000
  },
  {
    :first_name=>"Maddie",
    :last_name=>"Bryan",
    :email=>"maddie@ncsasports.tst",
    :primary_team=>"Women's Traveling Elite",
    :graduation_year=>2021,
    :zip_code=>46556,
    :phone=>5556305001
  },
  {
    :first_name=>"Meghan",
    :last_name=>"Costello",
    :email=>"meghan@ncsasports.tst",
    :primary_team=>"Women's Traveling Elite",
    :graduation_year=>2020,
    :zip_code=>46556,
    :phone=>5556305002
  },
  {
    :first_name=>"Caroline",
    :last_name=>"Murphy",
    :email=>"caroline@ncsasports.tst",
    :primary_team=>"Women's Traveling Elite",
    :graduation_year=>2019,
    :zip_code=>46556,
    :phone=>5556305003
  }
]
```


**Sample Params**

```ruby
{
  "uploaded_file"=>"/tmp/example.txt",
  "current_user"=>{
    "id"=>1,
    "created_at"=>"2017-02-28T06:58:38.314-06:00",
    "updated_at"=>"2017-02-28T06:58:38.314-06:00",
    "first_name"=>"Super",
    "email"=>"maria_paucek@walker.com",
    "phone"=>nil,
    "position_title"=>"Head Coach",
    "password_digest"=>"$2a$04$Hemqsnd0QCtfY.Ip2Pe1heBPBEewQg5MIwUKhyKxGBT8cT5Iqn6X.",
    "password_reset_token"=>nil,
    "organization_id"=>1,
    "last_name"=>"Coach",
    "password_reset_sent_at"=>nil,
    "deleted"=>false,
    "admin"=>true,
    "primary_contact"=>false
    },
    "controller"=>"athletes",
    "action"=>"create_bulk"
  }
```



## Errors & Statuses



success response: 201 created { athletes: athletes }

if coudlnt' ssave single athlete, context.fail!(error: "#{athlete[:first_name]} #{athlete[:last_name]} could not be created")

{ error: "no file found" }) if uploaded_file.nil?

if headers are incorrect, context.fail!(response: { error: "one or more of the headers is missing" })
* tmp file gets deleted

if primary team ! present context.fail!(error: "#{team_name} does not exist")

bad file format - "incorrect file format"

**See these files for examples**

* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/spec/interactors/create_athletes_in_bulk_spec.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/app/interactors/create_athletes_in_bulk.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/app/controllers/athletes_controller.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/spec/controllers/athletes_controller_spec.rb`

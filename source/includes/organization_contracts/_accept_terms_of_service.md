# UPDATE ORGANIZATION CONTRACT TERMS OF SERVICE TO ACCEPTED

**PATCH `/api/team_edition/organization_contracts/:organization_contract_id/accept_terms_of_service`**

This endpoint updates the terms of service to accepted if successful.


## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |


**Code Examples**

_cURL_

```shell
# @TODO
```


_Ruby Net::Http_

```ruby
# @TODO
```


## Responses

**Sample Successful Response**

```json
/* @TODO */
```

## Errrors/Statuses

See relevant spec files.


<!-- Clicking "I accept" after getting the emaiL: -->

```shell

Started PATCH "/api/team_edition/organization_contracts/2/accept_terms_of_service" for ::1 at 2017-02-28 01:15:45 -0600
Processing by OrganizationContractsController#accept_terms_of_service as */*
  Parameters: {"data"=>{"type"=>"organization_contracts", "attributes"=>{"accepted_by"=>"bill murray", "phrase"=>"$2a$10$g1mdqbfFIw4ui4/peFbvOeGyxANpI.A22BgtJtnwgLFiz1gdm6Iie"}, "relationships"=>{"organization_contract"=>{"data"=>{"id"=>2, "type"=>"organization_contracts"}}, "coach"=>{"data"=>{"id"=>3, "type"=>"coaches"}}}}, "organization_contract_id"=>"2", "organization_contract"=>{}}
  PartnerAdmin Load (0.5ms)  SELECT  "partner_admins".* FROM "partner_admins" WHERE "partner_admins"."id" = $1 AND "partner_admins"."password_digest" = $2 LIMIT $3  [["id", 1], ["password_digest", "$2a$10$QP7J4Kv2BX6P56sMqYGJxeW.2ZMb53W8Jqm2Cz/M/nu5SZMSiHlFC"], ["LIMIT", 1]]
  Coach Load (0.5ms)  SELECT  "coaches".* FROM "coaches" WHERE "coaches"."id" = $1 AND "coaches"."password_digest" = $2 LIMIT $3  [["id", 3], ["password_digest", "$2a$10$g1mdqbfFIw4ui4/peFbvOeGyxANpI.A22BgtJtnwgLFiz1gdm6Iie"], ["LIMIT", 1]]
  OrganizationContract Load (0.5ms)  SELECT  "organization_contracts".* FROM "organization_contracts" WHERE "organization_contracts"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
   (0.2ms)  BEGIN
  SQL (0.4ms)  UPDATE "organization_contracts" SET "accepted_at" = $1, "updated_at" = $2 WHERE "organization_contracts"."id" = $3  [["accepted_at", 2017-02-28 01:15:45 -0600], ["updated_at", 2017-02-28 01:15:45 -0600], ["id", 2]]
   (0.3ms)  COMMIT
[active_model_serializers]   Organization Load (0.6ms)  SELECT  "organizations".* FROM "organizations" WHERE "organizations"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
[active_model_serializers]    (0.4ms)  SELECT COUNT(*) FROM "athletes" WHERE "athletes"."deleted" = $1 AND "athletes"."organization_id" = $2  [["deleted", false], ["organization_id", 2]]
[active_model_serializers]   ContractAmount Load (0.5ms)  SELECT  "contract_amounts".* FROM "contract_amounts" WHERE "contract_amounts"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
[active_model_serializers]   Sport Load (0.4ms)  SELECT  "sports".* FROM "sports" WHERE "sports"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
[active_model_serializers] Rendered OrganizationContractSerializer with ActiveModelSerializers::Adapter::JsonApi (12.69ms)
Completed 200 OK in 28ms (Views: 11.4ms | ActiveRecord: 4.2ms)
```



```shell
Started POST "/api/team_edition/organizations/2/organization_accounts" for ::1 at 2017-02-28 01:10:58 -0600
Processing by OrganizationAccountsController#create as */*
  Parameters: {"data"=>{"type"=>"organization_accounts", "attributes"=>{"account_holder_first_name"=>"Joe", "account_holder_last_name"=>"Schmo", "account_holder_email"=>"cristinjaneo@gmail.com", "united_states"=>true, "billing_zip"=>"60613", "credit_card_number"=>"4111111111111111", "expiration_month"=>"4", "expiration_year"=>"2023", "cvv"=>"671", "phrase"=>"$2a$10$g1mdqbfFIw4ui4/peFbvOeGyxANpI.A22BgtJtnwgLFiz1gdm6Iie"}, "relationships"=>{"organization"=>{"data"=>{"id"=>2, "type"=>"organizations"}}, "organization_contract"=>{"data"=>{"id"=>2, "type"=>"organization_contracts"}}, "coach"=>{"data"=>{"id"=>3, "type"=>"coaches"}}}}, "organization_id"=>"2", "organization_account"=>{"data"=>{"type"=>"organization_accounts", "attributes"=>{"account_holder_first_name"=>"Joe", "account_holder_last_name"=>"Schmo", "account_holder_email"=>"cristinjaneo@gmail.com", "united_states"=>true, "billing_zip"=>"60613", "credit_card_number"=>"4111111111111111", "expiration_month"=>"4", "expiration_year"=>"2023", "cvv"=>"671", "phrase"=>"$2a$10$g1mdqbfFIw4ui4/peFbvOeGyxANpI.A22BgtJtnwgLFiz1gdm6Iie"}, "relationships"=>{"organization"=>{"data"=>{"id"=>2, "type"=>"organizations"}}, "organization_contract"=>{"data"=>{"id"=>2, "type"=>"organization_contracts"}}, "coach"=>{"data"=>{"id"=>3, "type"=>"coaches"}}}}}}
  PartnerAdmin Load (0.7ms)  SELECT  "partner_admins".* FROM "partner_admins" WHERE "partner_admins"."id" = $1 AND "partner_admins"."password_digest" = $2 LIMIT $3  [["id", 1], ["password_digest", "$2a$10$QP7J4Kv2BX6P56sMqYGJxeW.2ZMb53W8Jqm2Cz/M/nu5SZMSiHlFC"], ["LIMIT", 1]]
  Coach Load (0.6ms)  SELECT  "coaches".* FROM "coaches" WHERE "coaches"."id" = $1 AND "coaches"."password_digest" = $2 LIMIT $3  [["id", 3], ["password_digest", "$2a$10$g1mdqbfFIw4ui4/peFbvOeGyxANpI.A22BgtJtnwgLFiz1gdm6Iie"], ["LIMIT", 1]]
  Organization Load (0.5ms)  SELECT  "organizations".* FROM "organizations" WHERE "organizations"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  OrganizationContract Load (0.5ms)  SELECT  "organization_contracts".* FROM "organization_contracts" WHERE "organization_contracts"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  CACHE (0.0ms)  SELECT  "organizations".* FROM "organizations" WHERE "organizations"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  CACHE (0.0ms)  SELECT  "organization_contracts".* FROM "organization_contracts" WHERE "organization_contracts"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  CACHE (0.0ms)  SELECT  "organizations".* FROM "organizations" WHERE "organizations"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
  CACHE (0.0ms)  SELECT  "organizations".* FROM "organizations" WHERE "organizations"."id" = $1 LIMIT $2  [["id", 2], ["LIMIT", 1]]
I, [2017-02-28T01:10:58.764485 #11213]  INFO -- : post http://localhost:3000/api/payments/team_edition/authorize
D, [2017-02-28T01:10:58.764742 #11213] DEBUG -- request: User-Agent: "Faraday v0.11.0"
Content-Type: "application/json"
Started POST "/api/payments/team_edition/authorize" for ::1 at 2017-02-28 01:10:58 -0600

ActionController::RoutingError (No route matches [POST] "/api/payments/team_edition/authorize"):

/usr/local/opt/rbenv/versions/2.4.0/lib/ruby/2.4.0/webrick/httpserver.rb:140:in 'service'
/usr/local/opt/rbenv/versions/2.4.0/lib/ruby/2.4.0/webrick/httpserver.rb:96:in 'run'
/usr/local/opt/rbenv/versions/2.4.0/lib/ruby/2.4.0/webrick/server.rb:290:in 'block in start_thread'
I, [2017-02-28T01:10:58.819285 #11213]  INFO -- Status: 404
D, [2017-02-28T01:10:58.819555 #11213] DEBUG -- response: content-type: "application/vnd.api+json; charset=utf-8"
content-length: "6361"
x-request-id: "48377df2-1582-4276-83a5-3b1843582200"
x-runtime: "0.040160"
vary: "Origin"
x-newrelic-app-data: "PxQEV1dQDRAEUFFXAQQOVUYdFHANCBcQXw5UB0oXeVtXAVUERgBBB0tkVgINTHlQRA0ODHNYRBYFRVVbWFwxDUUWUQxfAg5gXBBNBGIER00HV1sNRE8IHQBIUUwHBQZSUAYHBVBQUVoBVQtaCxQZAx9HDllUVQcDVlIAUFBWXgYAUkM/"
server: "WEBrick/1.3.1 (Ruby/2.4.0/2016-12-24)"
date: "Tue, 28 Feb 2017 07:10:58 GMT"
connection: "close"
[active_model_serializers] Rendered ActiveModel::Serializer::Null with Class (0.18ms)
Completed 424 Failed Dependency in 111ms (Views: 10.9ms | ActiveRecord: 2.4ms)
```

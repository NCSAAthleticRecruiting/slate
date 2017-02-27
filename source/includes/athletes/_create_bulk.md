# CREATE ATHLETES IN BULK

**POST `/api/team_edition/athletes/create_bulk`**


## Requests

**Headers**

| Header          | Required? | Description                |
|-----------------|-----------|----------------------------|
| `Content-Type`  | true      | application/vnd.api+json   |
| `Session-Token` | true      | `eyJ0eXAiOiJKV1QiLCiJ9...` |



This endpoint handles the flow for creating athletes via an uploaded csv file.

**See these files for examples**

* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/spec/interactors/create_athletes_in_bulk_spec.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/app/interactors/create_athletes_in_bulk.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/app/controllers/athletes_controller.rb`
* `https://github.com/NCSAAthleticRecruiting/team_edition_service/blob/master/spec/controllers/athletes_controller_spec.rb`




## Errors & Statuses

* For errors, see relevant spec files to flesh out this section.

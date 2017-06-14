---
title: Team Edition API Docs

language_tabs:

toc_footers:
  - <h2>Helpful Documentation</h2><br>
  - <strong><a href='http://jsonapi.org'>JSON API Documentation</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-creating">Creating a Resource</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-updating">Updating a Resource</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-updating-relationships">Updating Relationships</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-deleting">Deleting a Resource</a><br><br></strong>
  - Documentation Powered by <a href='https://github.com/tripit/slate'>Slate</a>

includes:
  - sessions/create
  - sessions/destroy
  - athletes/create
  - athletes/create_bulk
  - athletes/index
  - athletes/refresh_athletes
  - athletes/show

  - athletes/profile
  - athletes/activity

  - athletes/get_athlete_teams
  - athletes/update_athlete_teams
  - athlete_integrations/recommendation
  - athlete_integrations/evaluation
  - athlete_integrations/coach_emails
  - athlete_integrations/grant_access_and_features
  - coaches/index
  - coaches/create
  - coaches/update
  - coaches/destroy
  - colleges/index
  - colleges/show
  - ncsa_sports/index
  - organization_contracts/create
  - organization_contracts/show
  - organization_contracts/index
  - organization_sports/index
  - organization_sports/evaluation_guidelines
  - organizations/create
  - organizations/index
  - organizations/show
  - organizations/update
  - partner_admins/index
  - partner_admins/create
  - partners/show
  - password_resets/create
  - password_resets/update
  - ping/respond
  - pricing_tiers/index
  - pricing_tiers/tier_sports
  - public_information/organization
  - team_integrations/toggle_active
  - team_integrations/delete_team
  - teams/index
  - teams/create
  - teams/show
  - teams/update
  - errors

search: true
---

# Introduction

Welcome to the Team Edition API! You can use our API to access NCSA Team Edition API endpoints.

You can view code examples in the dark area to the right.

Production URL: `http://www.ncsasports.org`

Staging URL: `http://qa.ncsasports.org`

### Tips
The oft-referenced `session-token` header can be found stored in a cookie named `team_rms_session`.<br>

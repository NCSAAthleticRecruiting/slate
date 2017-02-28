---
title: Team Edition API Docs

language_tabs:

toc_footers:
  - <h2>Tips</h2>
  - The often-referenced `session-token` header can be found stored in a cookie named `team_rms_session`.<br>
  - <h2>Helpful Documentation</h2><br>
  - <strong><a href='http://jsonapi.org'>JSON API Documentation</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-creating">Creating a Resource</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-updating">Updating a Resource</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-updating-relationships">Updating Relationships</a></strong>
  - <strong><a href="http://jsonapi.org/format/#crud-deleting">Deleting a Resource</a><br><br></strong>
  - Documentation Powered by <a href='https://github.com/tripit/slate'>Slate</a>

includes:
  - errors
  - athletes/create
  - athletes/create_bulk
  - athletes/index
  - athletes/refresh_athletes
  - athletes/show
  - athletes/get_profile_url
  - athletes/profile
  - athletes/activity
  - athletes/preferences
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
  - sessions/create
  - sessions/destroy
  - team_integrations/toggle_active
  - team_integrations/toggle_deleted
  - teams/index
  - teams/create
  - teams/show
  - teams/update

search: true
---

# Introduction

Welcome to the Team Edition API! You can use our API to access NCSA Team Edition API endpoints.

You can view code examples in the dark area to the right.



---

## Slate Markdown Syntax

```markdown
This is a reference for the Markdown syntax used in Slate.

### Headers

For headers:

    # Level 1 Header
    ## Level 2 Header
    ### Level 3 Header

Note that only level 1 and 2 headers will appear in the table of contents.

### Paragraph Text

For normal text, just type your paragraph on a single line.

    This is some paragraph text. Exciting, no?

Make sure the lines above and below your paragraph are empty.

### Code Samples

For code samples:

```
  ```ruby
  # This is some Ruby code!
  ```

  ```python
  # This is some Python code!
  ```
```

Code samples will appear in the dark area to the right of the main text. We recommend positioning code samples right under headers in your markdown file.

For the full list of supported languages, see [rouge](http://rouge.jneen.net/).

### Code Annotations

For code annotations:

    > This is a code annotation. It will appear in the area to the right, next to the code samples.

Code annotations are essentially the same thing as paragraphs, but they'll appear in the area to the right along with your code samples.

### Tables

Slate uses PHP Markdown Extra style tables:

```markdown
Table Header 1 | Table Header 2 | Table Header 3
-------------- | -------------- | --------------
Row 1 col 1 | Row 1 col 2 | Row 1 col 3
Row 2 col 1 | Row 2 col 2 | Row 2 col 3
'```'

Note that the pipes do not need to line up with each other on each line.

If you don't like that syntax, feel free to use normal html `<table>`s directly in your markdown.

### Formatted Text

    This text is **bold**, this is *italic*, this is an `inline code block`.

You can use those formatting rules in code annotations, tables, paragraphs, lists, wherever.

### Lists

    1. This
    2. Is
    3. An
    4. Ordered
    5. List

    * This
    * Is
    * A
    * Bullet
    * List

### Links

    This is an [internal link](#error-code-definitions), this is an [external link](http://google.com).

### Notes and Warnings

You can add little highlighted warnings and notes with just a little HTML embedded in your markdown document:

    <aside class="notice">
    You must replace `meowmeowmeow` with your personal API key.
    </aside>

Use `class="notice"` for blue notes, `class="warning"` for red warnings, and `class="success"` for green notes.

### Need Help?

If you have trouble with any of the syntax, or if it's confusing, let us know by filing an issue. Thanks!

```




### Miscellaneous

**Help with JSON API Requests**

* <a href="http://jsonapi.org/format/#crud-creating">Creating a Resource</a>
* <a href="http://jsonapi.org/format/#crud-updating">Updating a Resource</a>
* <a href="http://jsonapi.org/format/#crud-updating-relationships">Updating Resource Relationships</a>
* <a href="http://jsonapi.org/format/#crud-deleting">Deleting a Resource</a>


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks
401 | Unauthorized -- Your API key is wrong
403 | Forbidden -- The resource requested is hidden for administrators only
404 | Not Found -- The specified resource could not be found
405 | Method Not Allowed -- You tried to access a resource with an invalid method
406 | Not Acceptable -- You requested a format that isn't json
410 | Gone -- The resource requested has been removed from our servers
418 | I'm a teapot
429 | Too Many Requests -- You're requesting too many resources! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarially offline for maintanance. Please try again later.


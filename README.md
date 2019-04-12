# Nba stats system

## Description
- [ ] This Web System is designed to show NBA stats of all players and information about them

## Entity definition
- [ ] System's object is player
- [ ] Each player has a name.

- Player id: (number(length=1000)), 
- first_name: (string(length=30)),
- last_name: (string(length=30)),
- position: (string(length=2)),
- height_feet: (number(length=1)),
- height_inches: (number(length=2)),
- weight_pounds: (number(length=3)),

## API definition
The main purpose of this Web System is to get information about players from NBA.
API has these methods (used in this WEB system):
Get all players
GET https://www.balldontlie.io/api/v1/players
Get specific player
GET https://www.balldontlie.io/api/v1/players/<ID>

- 400	Bad Request -- Your request is invalid.
- 404	Not Found -- The specified resource could not be found.
- 406	Not Acceptable -- You requested a format that isn't json.
- 429	Too Many Requests -- Stop bombarding us.
- 500	Internal Server Error -- We had a problem with our server. Try again later.
- 503	Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.

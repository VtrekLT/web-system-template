# Nba stats system

## Description
- [ ] This Web System is designed to show NBA stats of all players and information about games.

## Entity definition
- [ ] System's object is player
- [ ] Each player has name.
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string
- [ ] Entity should have at least 5 custom attributes
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md

## API definition
The main thing this WEB system will get from API is all games and players.
API has these methods (used in this WEB system):
Get all players
GET https://www.balldontlie.io/api/v1/players
Get specific player
GET https://www.balldontlie.io/api/v1/players/<ID>
Get all games
GET https://www.balldontlie.io/api/v1/games
Get specific game
GET https://www.balldontlie.io/api/v1/games/<ID>
    
- 400	Bad Request -- Your request is invalid.
- 404	Not Found -- The specified resource could not be found.
- 406	Not Acceptable -- You requested a format that isn't json.
- 429	Too Many Requests -- Stop bombarding us.
- 500	Internal Server Error -- We had a problem with our server. Try again later.
- 503	Service Unavailable -- We're temporarily offline for maintenance. Please try again later.

- [ ] API should have at least 4 methods
    - [ ] A method to return entity by ID. Should not have request body
    - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [ ] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [ ] A method to remove entity by ID. Returns removed entity. Should not have request body
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity
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

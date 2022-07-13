# API Format & Design

In terms of general API design guidance, the [DoD EADS handbook](https://dodcio.github.io/eads/) is a good default.

## High-Level Guidance

* Follow modern REST patterns
* Only use nonstandard endpoint name/method conventions for non-CRUD operations
* Include `href` references to other resources or resource detail

## Example of Standard REST CRUD Patterns

HTTP VERB | URL | Behavior | Response
--------- | --- | -------- | --------
`POST`  | `/pets` | Create: a new pet is inserted (sending a body of the pet details in the request). | Detail of newly created pet.
`GET`   | `/pets` | Read Index: list all pets. Optionally provide URL parameters to filter the list. | List of many pets.
`GET`   | `/pets/255` | Read Detail: get details of one individual record by the identifier. | Detail of single pet.
`PATCH` | `/pets/255` | Update: update attributes of a single resource. | Detail of updated pet.
`PATCH` | `/pets` | Update (many): Update all resources (matching any filter criteria) with the supplied attributes/values. | List of updated pets.

## Response Body Structure

* Always a json object at the top level `{ ... }`
* Includes either `meta` and `data` OR `error` as top-level attributes.
* camelCase json variables


```json
// GET /pets
// 200
{
  "meta": {
    "resourceType": "pet",
    "totalResults": 155,
    "offset": 0,
    "limit": 10
  },
  "data": [
    { "name": "sparky", "breed": "beagle", "href": "/pets/55" },
    { "name": "pinky", "breed": "poodle", "href": "/pets/102" },
    ...
  ]
}
```

```json 
// GET /pets/999
// 404
{
  "error": {
    "developerMessage" : "An invalid pet ID was supplied.",
    "userMessage" : "Sorry, we can't find that pet.",
    "errorCode" : 9583,
    "moreInfo" : "https://link/to/additional/information"
  }
}
```

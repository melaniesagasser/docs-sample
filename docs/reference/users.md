# Reference Documentation for the User API

Overview of the User API endpoints and their parameters.

## List all Users

Retrieves a list of all existing users.

### Endpoint

`GET /v1/users/`

### Parameters

This endpoint doesn’t require any parameters.

### Sample Response

The content type is `application/json`. Each user is represented as a [`User` object](#user) with an `id` and `name`.

````json
[
  {
    "id": "jmiller",
    "name": "Jane Miller"
  },
{
    "id": "psmith",
    "name": "Paul Smith"
  }
]
````

### Status Codes

| Code | Message | Description |
| --- | --- | ---|
| 200 | OK | The request was successful and returns a list of users. |

## Create a User

Creates a new user with the specified ID and name.

### Endpoint

`POST /v1/users`

### Request Body

The request must be sent with the content type `application/json`. </br>
The user is represented as a [`User` object](#user) with the following properties:

| Property | Description | Type | Required | Notes |
| --- | --- | --- | --- | ---- |
| id | The unique user ID | string | | The user ID can contain letters, numbers, or special signs. |
| name | The user’s name | string | |

### Sample Request

````bash
curl -X POST https://api.example.com/v1/users \
  -H "Content-Type: application/json" \
  -d '{
    "id": "jmiller",
    "name": "Jane Miller"
  }'
````

### Sample Response

The content type is `application/json`.

````json

{
  "id": "jmiller",
  "name": "Jane Miller"
}
````

### Status Codes

| Code | Message | Description |
| --- | --- | --- |
| 201 | User created | The user has been successfully created. |

## Objects

### User

Contains information about the user.

| Property | Description | Type | Required | Notes |
| --- | --- | --- | --- | ---- |
| id | The unique user ID | string | | The user ID can contain letters, numbers, or special signs. |
| name | The user’s name | string | |

## Gaps or Unclear Parts in the API Documentation

- The base URL is missing in the OpenAPI Specification file/snippet.
- It’s not clear which fields are mandatory in the request body for the POST method.
- There's no information about the authentication method.
- As for the GET method, is there a limit of how many users will be displayed at once? Which message would the user get? This information about what the user can expect to get could also be added to the description in the specification file so it doesn't come as a surprise.
- Email field specification is missing (see the comment in the OpenAPI Specification file). Will it be added or is it redundant?
- It’s not clear if there are restrictions on what the user can enter as ID/name (e.g., length restriction, etc.), or what is expected. I added a note for the user ID, but that would need to be discussed with development.
- There should be one or more error messages that come up when the user makes a wrong entry or forgets a field, or if the user ID or name already exists, or if the user enters nothing or just a space. Additionally, information about the expected input should be added to the specification file so the user doesn't even make such a mistake.
- Some of the questions might get answered by testing it in a tool like Swagger, for example, but for that, the API would need to be set up properly.


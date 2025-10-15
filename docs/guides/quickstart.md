# User API Quick Start

The User API lets you manage users. You can create new users and get a list of existing users.

To learn how the API works, you can use the sample curl requests provided below.

## Create a User

To create a new user in the system, use the following curl request:</br>

```bash
curl -X POST https://api.example.com/v1/users \
 -H "Content-Type: application/json" \
 -d '{"name": "John", "email": "john@example.com"}'
```

## List all Users

To retrieve a list of all users in the system, use the following curl request: </br>

````bash
curl -X GET https://api.example.com/v1/users
````


# Getting Started with the User API

This guide explains how to authenticate your API key and make a sample request to the User API.

## Overview

The User API lets you manage users. You can create users, and you can get a list of all users.

## Prerequisites

To use the User API, you need the following:

1. A developer account or sign-up link. For more information, reach out to your IONOS sales partner.
2. An API key you receive from the API Keys portal. For more information, refer to [Authentication](#authentication).
3. A tool for making API requests, such as Postman or `curl`.

## Authentication

The User API uses API keys to authenticate. You need to create your API key once to be able to make API requests.

To create your API key, follow the steps listed in the [IONOS Developer Guide](https://developer.hosting.ionos.de/docs/getstarted).

Remember to save both the public prefix and the secret of the key, as you’ll need them for making an API request in the next step.

## Make your First API Request

In this example, you create a user in the system using your API key.

Copy the following curl sample and replace `publicprefix.secret` with your personal API key that you created in the [Authentication](#authentication) step:

````bash
curl -X POST "https://api.hosting.ionos.com/v1/users?id=jmiller&name=Jane%20Miller" \
  -H "X-API-Key: publicprefix.secret"
````

Paste the adjusted curl sample into your API request tool. You get the following response:

````json
  {
    "id": "jmiller",
    "name": "Jane Miller"
  }
````

## Result

You created your first user in the system, user Jane Miller, with the user ID jmiller.

# Authentication Management

Manages user authentication using JWT based Web Token.

## Endpoint

```
    POST /auth/token/
```

## _Example Request_

```
    let response = await fetch("http://127.0.0.1:8000/auth/token/", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        username: e.target.user_name.value,
        password: e.target.user_password.value,
      }),
    });

    let data = await response.json();
    if (response.status === 200) {
      // Do something
    }
```

## Request Data

| Parameter | Datatype | Description                   | Required |
| --------- | -------- | ----------------------------- | -------- |
| username  | string   | Username of the user account. | Yes      |
| password  | string   | Password the user account.    | Yes      |

## Response format

JSON

## _Example Response_

The reponse is encoded with HS256 Algorithm. To decode, check the [jwt-decode](https://www.npmjs.com/package/jwt-decode) page.

```
    {
    "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTcxMzU2NjY1MCwiaWF0IjoxNzEwOTc0NjUwLCJqdGkiOiJjMjJiZTBlNWIwY2E0OWFjODU2NmRkYWY5NDRiODBmMCIsInVzZXJfaWQiOjEsInVzZXJuYW1lIjoiYWRtaW4iLCJlbWFpbCI6ImFkbWluQGdtYWlsLmNvbSJ9.OMNTFEWPKgvjt9BkeUu4e_uQNqlFO_ZYYRYSC60iR9E",

    "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNzEwOTc2NDUwLCJpYXQiOjE3MTA5NzQ2NTAsImp0aSI6ImU3NzY4ZTkyNWVhZTQxZjI4YzgyNTA1YzdlMTI4ZDY1IiwidXNlcl9pZCI6MSwidXNlcm5hbWUiOiJhZG1pbiIsImVtYWlsIjoiYWRtaW5AZ21haWwuY29tIn0.lGlZuOwLU24DPnYxAHomU0fMIXAz8YFbjeYM8JhrJ2Y"
    }

```

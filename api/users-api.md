# User Management

Manages user account within the application. Allow creation, modification, deletion and retrieval of user records.

## Authentication

Requires JWT token.

<details>
<summary>1. Retrieve user account information.</summary>

## Endpoint

```
GET    /api/users/<int:user_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/users/${user_id}/", {
    method: "GET",
    headers: {
    "Content-Type": "application/json",
    }
    });

    let data = await response.json();
    if (response.status === 200) {
        // Do something
    }

```

## Request Data

| Parameter | Datatype | Description                                | Required |
| --------- | -------- | ------------------------------------------ | -------- |
| user_id   | int      | ID of the user retrieving the information. | Yes      |

## Response format

JSON

## _Example Response_

```

    {
    "id": 123,
    "name": "harry",
    "address": "london, UK",
    "created_at": "2024-03-20T18:27:52.659Z",
    "status": true,
    "last_login": "2024-03-20T18:27:52.659Z",
    }
```

</details>

<details>
<summary>2. Delete user account information.</summary>

## Endpoint

```
GET    /api/users/<int:user_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/users/${user_id}/", {
    method: "DELETE",
    headers: {
    "Content-Type": "application/json",
    }
    });

    let data = await response.json();
    if (response.status === 200) {
        // Do something
    }

```

## Request Data

| Parameter | Datatype | Description                                | Required |
| --------- | -------- | ------------------------------------------ | -------- |
| user_id   | int      | ID of the user retrieving the information. | Yes      |

## Response format

JSON

## _Example Response_

```

    {
    "message": "Account deletion successful."
    }
```

</details>

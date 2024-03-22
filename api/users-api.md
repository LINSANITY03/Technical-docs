# User Management

Manages user account within the application. Allow creation, modification, deletion and retrieval of user records.

## Authentication

Requires JWT token.

## API'S

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
    "password": "pbkdf2_sha256$390000$TXnGj7P=",
    "email": "zevero@example.com"
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

<details>
<summary>3. Create a user account.</summary>

## Endpoint

```
POST    /api/users/
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/users/", {
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

```

    {
    "message": "Account created successful."
    }
```

</details>

<details>
<summary>4. Update a user account.</summary>

## Endpoint

```
PUT    /api/users/<int:user_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/users/${user_id}/", {
    method: "PUT",
    headers: {
    "Content-Type": "application/json",
    },
    body: JSON.stringify({
        name: e.target.user_name.value,
        email: e.target.user_email.value,
        address: e.target.user_address.value,
      }),
    });

    let data = await response.json();
    if (response.status === 200) {
        // Do something
    }

```

## Request Data

| Parameter | Datatype | Description                        | Required |
| --------- | -------- | ---------------------------------- | -------- |
| name      | string   | Profile name of the user account.  | Yes      |
| email     | string   | Registered email the user account. | Yes      |
| address   | string   | Physical address.                  | No       |

## Response format

JSON

## _Example Response_

```

    {
    "message": "Account updated."
    }
```

</details>

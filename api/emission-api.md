# Emission Management

Manages the emission data api's and the logic behind complex calculations.

## Authentication

Requires JWT token.

## API'S

<details>
<summary>1. Retrieve all emission record information of registered user.
</summary>

## Endpoint

```
GET    /api/emissions/<int:user_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/api/emissions/${user_id}/", {
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

[
  {
    "id": 45,
    "user_Id": 2,
    "item": "Item A",
    "address_from": "123 Elm Street, Maplewood, CA 123, USA",
    "address_to": "123 Willow Avenue, Brisbane, QLD 123, Australia",
    "quantity": 10,
    "updated_at": "",
    "created_at": "2024-02-25T16:44:56.835000+05:45"
  },
  {
    "id": 43,
    "user_Id": 2,
    "item": "Item AB",
    "address_from": "123 Birch Lane, London 123 123, United Kingdom",
    "address_to": "123 Oak Terrace, Toronto, ON 123 123, Canada",
    "quantity": 10,
    "updated_at": "",
    "created_at": "2023-10-15T12:25:38+05:45"
  },
]
```

</details>

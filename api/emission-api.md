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

<details>
<summary>2. Update the selected emission record.</summary>

## Endpoint

```
PUT    /api/emissions/<int:user_id>/<int:emission_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/api/emissions/${user_id}/${emission_id}", {
    method: "POST",
    headers: {
    "Content-Type": "application/json",
    },
    body: JSON.stringify({
        item: e.target.item_name.value,
        /*
            other attributes
        */
      }),
    });

    let data = await response.json();
    if (response.status === 200) {
        // Do something
    }

```

## Request Data

| Parameter    | Datatype | Description                                | Required |
| ------------ | -------- | ------------------------------------------ | -------- |
| user_id      | int      | ID of the user retrieving the information. | Yes      |
| emission_id  | int      | ID of the emission record to be retrieve.  | Yes      |
| item         | Varchar  | category of the emission                   | Yes      |
| address_from | Varchar  | starting point of delivery                 | Yes      |
| address_to   | Varchar  | destination point of delivery              | Yes      |
| quantity     | BigInt   | Volume of material to deliver              | Yes      |

## Response format

JSON

## _Example Response_

```

    {
    "message": "Record updated."
    }
```

</details>

<details>
<summary>3. Delete the selected emission record.</summary>

## Endpoint

```
DELETE    /api/emissions/<int:user_id>/<int:emission_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/api/emissions/${user_id}/${emission_id}", {
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

| Parameter   | Datatype | Description                                | Required |
| ----------- | -------- | ------------------------------------------ | -------- |
| user_id     | int      | ID of the user retrieving the information. | Yes      |
| emission_id | int      | ID of the emission record to be retrieve.  | Yes      |

## Response format

JSON

## _Example Response_

```

    {
    "message": "Record deleted successfully."
    }
```

</details>

<details>
<summary>4. Add a emission record.</summary>

## Endpoint

```
POST    /api/emissions/<int:user_id>
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/api/emissions/${user_id}", {
    method: "POST",
    headers: {
    "Content-Type": "application/json",
    },
    body: JSON.stringify({
        item: e.target.item_name.value,
        /*
            other attributes
        */
      }),
    });

    let data = await response.json();
    if (response.status === 200) {
        // Do something
    }

```

## Request Data

| Parameter    | Datatype | Description                                | Required |
| ------------ | -------- | ------------------------------------------ | -------- |
| user_id      | int      | ID of the user retrieving the information. | Yes      |
| item         | Varchar  | category of the emission                   | Yes      |
| address_from | Varchar  | starting point of delivery                 | Yes      |
| address_to   | Varchar  | destination point of delivery              | Yes      |
| quantity     | BigInt   | Volume of material to deliver              | Yes      |

## Response format

JSON

## _Example Response_

```

    {
    "message": "Record added successfully"
    }
```

</details>

<details>
<summary>5. Get the calculation for data visualization.</summary>

## Endpoint

```
GET    /api/emissions/<int:user_id>/get_calculations
```

## _Example Request_

```

    let response = await fetch("http://127.0.0.1:8000/api/emissions/${user_id}/get_calculations", {
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
        "id": 42,
        "calculation": 50,
        "created_at": "2023-10-15T12:25:38+05:45",
        "distance": 0.5,
        "quantity": 10
    },
    {
        "id": 43,
        "calculation": 80,
        "created_at": "2024-02-25T16:44:56.835000+05:45",
        "distance": 0.8,
        "quantity": 10
    }
]
```

</details>

# Addititional Notes:

Some of the API are long running API. To improve api usage, use a asynchronous approach as shown in example above or [view this reference](https://www.geeksforgeeks.org/how-to-fetch-data-from-apis-using-asynchronous-await-in-reactjs/).

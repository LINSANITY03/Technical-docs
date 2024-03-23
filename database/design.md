# Zevero-Emission-Database-Design

The purpose of this documentation is to capture the essential aspect of database table's structure, purpose and usage. The design follow a relational database model for managing carbon emission.

<details>
<summary>
    Table Name: User 
</summary>

User table contains all the information about the user accounts. The purpose of this table is store user information which can be used for login, retreiving sensitive user data.

## Fields

| Field Name | Data Type | Description                                                             | Constraints                               |
| ---------- | --------- | ----------------------------------------------------------------------- | ----------------------------------------- |
| Id         | Int       | Unique Identifier for each User                                         | Not Null, Unique, Auto Increment, Primary |
| Username   | Varchar   | User's username                                                         | Not Null, Unique                          |
| Password   | Varchar   | User's password                                                         | Not Null                                  |
| Last_login | datetime  | Timestamp indicating the user was last logged in.                       |                                           |
| First_name | Varchar   | User's first name                                                       | Not Null                                  |
| Last_name  | Varchar   | User's last name                                                        | Not Null                                  |
| Email      | Varchar   | User's registered email                                                 | Not Null, Unique                          |
| is_active  | Boolean   | Bool value, True indicates whether the account is active and vice versa | Not Null                                  |
| Created_at | Varchar   | Timestamp indicating the account creation                               | Not Null                                  |
| Addresss   | Varchar   | Physical address of the user                                            | Not Null                                  |

## Primary Key:

- ID: Unique identifier of each user.

## Indexes:

- Primary: ID - Unique identifier of each user.
- username: Username - Unique username of each user.

## Relationships:

**User** table has one-to-many relationship with **Emission** table.

## Sample Data:

| Id | Username | Password | Last_login | First_name | Last_name | Email | is_active | Created_at | Address |
| 1 | Hello1234 | pbkdf2_sha256$320000$hasd | 2023-02-19 06:45:50.492456 | Hello | World | helloworld12@example.com | 1 | 2022-06-15 06:18:40.721434 | london, UK |

## Additional Notes:

By default, password are hashed with PBKDF2 algorithm with a SHA256 hash

</details>

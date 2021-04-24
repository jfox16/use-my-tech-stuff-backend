# Use My Tech Stuff API

Endpoints with an (auth) require an authorization token like so: 

Headers:
| Key | Value |
| :-- | :-- |
| Authorization | <AUTH_TOKEN> |

## Authorization

### Register

<details>
  <summary>
    POST /api/auth/register
  </summary>

  Body:
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | username | string | (required) |
  | password | string | (required) |
  | email | string | (required) |
  | role | string | "user" or "renter" (defaults to "user") |

  Response:
  ```
  { token: <AUTH_TOKEN> }
  ```
</details>

### Login

<details>
  <summary>
    POST /api/auth/login
  </summary>

  Body:
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | username | string | (required) |
  | password | string | (required) |

  Response:
  ```
  { token: <AUTH_TOKEN> }
  ```
</details>

## Users

## Items

### Get all items

<details>
  <summary>
    GET /api/items (auth)
  </summary>

  Response:
  ```
  [
    {
      item_id: 1,
      name: "Television",
      owner: "Iron Man",
      available: false
    },
    {
      item_id: 2,
      name: "Camera",
      owner: "Spiderman",
      available: true
    },
    ...
  ]
  ```
</details>

### Post an item

<details>
  <summary>
    POST /api/items (auth)
  </summary>
  
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | name | string | (required) |
  | description | string | |
</details>

### Edit your own item

<details>
  <summary>
    POST /api/items/:item_id (auth)
  </summary>
  
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | name | string | |
  | description | string | |
</details>

### Get your own items

<details>
  <summary>
    GET /api/account/items (auth)
  </summary>

  Response:
  ```
  [
    {
      item_id: 1,
      name: "Television",
      available: false
    }
    ...
  ]
  ```
</details>

## Item Rentals

### Request an item rental

<details>
  <summary>
    POST /api/items (auth)
  </summary>
  
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | name | string | (required) |
  | description | string | |
</details>

## Your Account

### Get your own account info

<details>
  <summary>
    GET /api/account (auth)
  </summary>

  Response:
  | Key | Type |
  | :-- | :-- |
  | email | string |
  | password | string |
  | role | string |
  | first_name | string |
  | last_name | string |
</details>

### Update your own account info

<details>
  <summary>
    PUT /api/account (auth)
  </summary>

  Response:
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | email | string | |
  | password | string | |
  | role | string | "user" or "renter" |
  | first_name | string | |
  | last_name | string | |
</details>

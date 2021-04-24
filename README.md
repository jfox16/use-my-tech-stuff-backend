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

### Get item details

<details>
  <summary>
    GET /api/items/:item_id (auth)
  </summary>

  Response:
  ```
  {
    item_id: 1,
    name: "Television",
    owner: { user_id: 1, username: "Iron Man" },
    available: false,
    rented_by: { user_id: 2, username: "Captain America" }
  }
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

## Requests

### Make a request

<details>
  <summary>
    POST /api/requests (auth)
  </summary>
  
  Body:
  | Parameter | Type | Notes |
  | :-- | :-- | :-- |
  | item_id | int | (required) |
</details>

### Get request details

<details>
  <summary>
    GET /api/requests/:request_id (auth)
  </summary>
  
  Response:
  ```
  {
    request_id: 1,
    item: { item_id: 1, name: "Television", "owner_id": 1 },
    
  }
  ```
</details>

### Cancel a request

<details>
  <summary>
    DELETE /api/requests/:request_id (auth)
  </summary>
  
  Response: deleted request
  ```
  {
    id: 0,
    item: { id: 1, name: "Toaster", owner: "Captain America" }
  }
  ```
</details>

### Accept a request

<details>
  <summary>
    PUT /api/requests/:request_id (auth)
  </summary>
  
  Response: deleted request
  ```
  {
    id: 0,
    item: { id: 1, name: "Toaster", owner: "Captain America" }
  }
  ```
</details>

## Your Account

### Get your own account info

<details>
  <summary>
    GET /api/account (auth)
  </summary>

  Response:
  ```
  {
    user_id: 1,
    username: "Iron Man",
    
  }
  ```
</details>

### Get requests you made

<details>
  <summary>
    GET /api/account/requests (auth)
  </summary>

  Response:
  ```
  [
    { request_id: 1, item_id: 1, owner: "Superman" },
    { request_id: 2, item_id: 3, owner: "Batman" },
    ...
  ]
  ```
</details>

### Get requests for your items

<details>
  <summary>
    GET /api/account/requests (auth)
  </summary>

  Response:
  ```
  [
    { request_id: 1, item_id: 1, requester: "Iron Man" },
    { request_id: 2, item_id: 3, requester: "Captain America" },
    ...
  ]
  ```
</details>

# Use My Tech Stuff API

(auth) routes require an authorization token like so: 

Headers:
| Key | Value |
| :-- | :-- |
| Authorization | <AUTH_TOKEN> |

---

## Register

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

---

## Login

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

---

## Get all items

GET /api/items (auth)

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

---

## Get your own account info

GET /api/account (auth)

Response:
| Key | Type |
| :-- | :-- |
| email | string |
| password | string |
| role | string |
| first_name | string |
| last_name | string |

---

## Update your own account info

PUT /api/account (auth)

Response:
| Parameter | Type | Notes |
| :-- | :-- | :-- |
| email | string | |
| password | string | |
| role | string | "user" or "renter" |
| first_name | string | |
| last_name | string | |



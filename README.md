# Use My Tech Stuff API

if a route has (auth), it requires the an auth token like so: 

Headers:
| Key | Value |
| :-- | :-- |
| Authorization | <AUTH_TOKEN> |

---

### Register

POST /api/register

Body:
| Parameter | Type | Notes |
| :-- | :-- | :-- |
| email | string | (required) |
| password | string | (required) |
| role | string | "user" or "renter" (defaults to "user") |
| first_name | string | |
| last_name | string | | 

Response:
| Key | type |
| :-- | :-- |
| token | string |

---

### Login

POST /api/login

Body:
| Parameter | Type | Notes |
| :-- | :-- | :-- |
| email | string | (required) |
| password | string | (required) |

Response:
| Key | type |
| :-- | :-- |
| token | string |

---

### Get your own account info

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

### Update your own account info

PUT /api/account (auth)

Response:
| Parameter | Type | Notes |
| :-- | :-- | :-- |
| email | string | |
| password | string | |
| role | string | "user" or "renter" (defaults to "user") |
| first_name | string | |
| last_name | string | | 



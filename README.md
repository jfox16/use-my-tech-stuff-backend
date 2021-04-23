# Use My Tech Stuff API

if a route has (auth), it requires the an auth token like so: 

Headers:
```
Authorization: <AUTH_TOKEN>
```

---

### Register

POST /api/register

Body:
| Parameter | Type | Description |
| --- | --- | --- |
| email | string | (required) |
| password | string | (required) |
| first_name | string | |
| last_name | string | | 

Response:
```
{
  "token": <AUTH_TOKEN>
}
```

---

### Login

POST /api/login

Body:
```
{
  "email": "test@mail.com" (required),
  "password": "hunter2" (required)
}
```

Response:
```
{
  "token": <AUTH_TOKEN>
}
```

---

### Get your own account info

GET /api/account (auth)
```
{ user_id, email, role, first_name, last_name }
```



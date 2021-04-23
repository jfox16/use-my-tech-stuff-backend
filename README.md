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
```
{
  "email": "test@mail.com" (required),
  "password": "hunter2" (required),
  "role": "user" or "renter" (defaults to "user")
  "firstName": "First",
  "lastName": "Lastington"
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



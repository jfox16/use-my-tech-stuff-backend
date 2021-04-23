# Use My Tech Stuff API

---

### Register

POST /api/register

Headers:
```
Authorization: <auth token>
```

Body:
```
{
  "email": "test@mail.com" (required),
  "password": "hunter2" (required),
  "role": "user" or "renter" (defaults to user)
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
  "token": ...
}
```

---

### Get your own account info

GET /api/account
```
{ user_id, email, role, first_name, last_name }
```



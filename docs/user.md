# User API Spec

## Register User API

Endpoint: POST /api/users

Request Body:

```json
{
  "username": "cupsky",
  "password": "secret",
  "name": "Cupsky"
}
```

Response Body Success:

```json
{
  "data": {
    "username": "cupsky",
    "name": "Cupsky"
  }
}
```

Response Body Error:

```json
{
  "errors": "Username already registered."
}
```

## Login User API

Endpoint: POST /api/users/login

Request Body:

```json
{
  "username": "cupsky",
  "password": "secret"
}
```

Response Body Success:

```json
{
  "data": {
    "token": "unique-token",
    "username": "cupsky",
    "name": "Cupsky"
  }
}
```

Response Body Error:

```json
{
  "errors": "Username or password is invalid."
}
```

## Update User API

Endpoint: PATCH /api/users/current

Headers:

- Authorization: {token}

Request Body:

```json
{
  "name": "Jonathan", //optional
  "password": "new password" // optional
}
```

Response Body Success:

```json
{
  "data": {
    "username": "cupsky",
    "name": "Jonathan"
  }
}
```

Response Body Error:

```json
{
  "errors": "Name length can be greater than 100 characters"
}
```

## GET User API

Endpoint: GET /api/users/current

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": {
    "username": "cupsky",
    "name": "Jonathan"
  }
}
```

Response Body Error:

```json
{
  "errors": "Unauthorize"
}
```

## Logout User API

Endpoint: DELETE /api/users/logout

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": "Logout success"
}
```

Response Body Error:

```json
{
  "errors": "Unauthorize"
}
```

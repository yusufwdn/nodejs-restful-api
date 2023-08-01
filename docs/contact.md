# Contact API Spec

## Create Contact API

Endpoint: POST /api/contacts

Headers

- Authorization: {token}

Request Body:

```json
{
  "first_name": "Yusuf",
  "last_name": "Wandana",
  "email": "yusuf@email.com",
  "phone": "1023923000"
}
```

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "first_name": "Yusuf",
    "last_name": "Wandana",
    "email": "yusuf@email.com",
    "phone": "1023923000"
  }
}
```

Response Body Error:

```json
{
  "errors": "Invalid entered phone."
}
```

## Update Contact API

Endpoint: PUT /api/contacts/:id

Headers:

- Authorization: {token}

Request Body:

```json
{
  "first_name": "Yusuf",
  "last_name": "Wandana",
  "email": "yusuf@email.com",
  "phone": "1023923000"
}
```

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "first_name": "Yusuf",
    "last_name": "Wandana",
    "email": "yusuf@email.com",
    "phone": "1023923000"
  }
}
```

Response Body Error:

```json
{
  "errors": "Invalid entered phone"
}
```

## GET Contact API

Endpoint: GET /api/contacts/:id

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "first_name": "Yusuf",
    "last_name": "Wandana",
    "email": "yusuf@email.com",
    "phone": "1023923000"
  }
}
```

Response Body Error:

```json
{
  "errors": "Contact not found"
}
```

## Search Contact API

Endpoint: GET /api/contacts

Headers:

- Authorization: {token}

Parameters:

- name : Search by first_name or last_name, using like query. optional
- email : Search by email, using like query. optional
- phone : Search by phone, using like query. optional
- page : number of page, deafult 1
- size : size per page, default 10

Response Body Success:

```json
{
  "data": [
    {
      "id": 1,
      "first_name": "Yusuf",
      "last_name": "Wandana",
      "email": "yusuf@email.com",
      "phone": "1023923000"
    },
    {
      "id": 2,
      "first_name": "Herman",
      "last_name": "Hermawan",
      "email": "h.hewmawan@email.com",
      "phone": "0231927779"
    }
  ],
  "paging": {
    "page": 1,
    "total_pages": 3,
    "total_items": 30
  }
}
```

Response Body Error:

```json
{
  "errors": "Unauthorize"
}
```

## Remove Contact API

Endpoint: DELETE /api/contacts/:id

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": "Contact has been updated"
}
```

Response Body Error:

```json
{
  "errors": "Contact not found"
}
```

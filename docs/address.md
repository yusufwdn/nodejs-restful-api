# Address API Spec

## Create Address API

Endpoint: POST /api/contact/:contactId/addresses

Headers

- Authorization: {token}

Request Body:

```json
{
  "street": "Nama Jalan",
  "city": "Nama Kota",
  "province": "Nama Provinsi",
  "country": "Nama Negara",
  "postal_code": "kode Pos"
}
```

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "street": "Nama Jalan",
    "city": "Nama Kota",
    "province": "Nama Provinsi",
    "country": "Nama Negara",
    "postal_code": "kode Pos"
  }
}
```

Response Body Error:

```json
{
  "errors": "Street is required."
}
```

## Update Address API

Endpoint: PUT /api/addresses/:addressId

Headers:

- Authorization: {token}

Request Body:

```json
{
  "street": "Nama Jalan",
  "city": "Nama Kota",
  "province": "Nama Provinsi",
  "country": "Nama Negara",
  "postal_code": "kode Pos"
}
```

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "street": "Nama Jalan",
    "city": "Nama Kota",
    "province": "Nama Provinsi",
    "country": "Nama Negara",
    "postal_code": "kode Pos"
  }
}
```

Response Body Error:

```json
{
  "errors": "Country must be a valid string"
}
```

## GET Address API

Endpoint: GET /api/contacts/:contactId/addresses/:addressId

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": {
    "id": 1,
    "street": "Nama Jalan",
    "city": "Nama Kota",
    "province": "Nama Provinsi",
    "country": "Nama Negara",
    "postal_code": "kode Pos"
  }
}
```

Response Body Error:

```json
{
  "errors": "Contact not found"
}
```

## List Address API

Endpoint: GET /api/contacts/:contactId/addresses

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
      "street": "Nama Jalan",
      "city": "Nama Kota",
      "province": "Nama Provinsi",
      "country": "Nama Negara",
      "postal_code": "kode Pos"
    },
    {
      "id": 2,
      "street": "Nama Jalan",
      "city": "Nama Kota",
      "province": "Nama Provinsi",
      "country": "Nama Negara",
      "postal_code": "kode Pos"
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
  "errors": "Contact not found"
}
```

## Remove Address API

Endpoint: DELETE /api/contacts/:contactId/addresses/:addressId

Headers:

- Authorization: {token}

Response Body Success:

```json
{
  "data": "Address has been updated"
}
```

Response Body Error:

```json
{
  "errors": "Address not found"
}
```

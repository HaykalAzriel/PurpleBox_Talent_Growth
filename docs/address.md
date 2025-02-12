# Address API Spec

## Create Address API 

Endpoint : POST /api/contact/:contactId/address

Headers :
- Authorization : token

Request Body : 

```json
{
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
```

Response Body Success:

```json
{
    "data" : 
{
    "id" : 1,
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
}
```

Response Body Error:

```json
{
    "errors" : "country is required" 
}
```

## Update Address API 

Endpoint : PUT /api/:contactId/contact/:addressId

Headers :
- Authorization : token

Request Body : 

```json

{
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
```

Response Body Success:

```json
{
    "data" : 
{
    "id" : 1, 
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
}
```
Response Body Error:

```json
{
    "errors" : "country is required" 
}
```

## Get Address API

Endpoint : GET /api/contact/:contactId/:addressId

Headers :
- Authorization : token


Response Body Success:

```json
{
    "data" : 
{
    "id" : 1, 
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
}
```

Response Body Error:

```json
{
    "errors" : "Contact is not found" 
}
```

## List Address API

Endpoint : GET /api/contact/:contactId/address

Headers :
- Authorization : token

Response Body Success:

```json
{
    "data" : [       
{
    "id" : 1, 
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos"
      },
{
    "id" : 1,
    "street" : "Jalan apa", 
    "citi" : "kota apa",
    "province" : "Provinsi apa",
    "country" : "Negara apa",
    "postal-code" : "Kode pos" 
}
      ]
}
```

Response Body Error:

```json
{
    "errors" : "contact is not found"
}
```

## Remove Address API

Endpoint : POST /api/contact/:id/address

Headers :
- Authorization : token 

Response Body Success:

```json
{
    "data" : "OK"
}
```

Response Body Error:

```json
{
    "errors" : "address is not found" 
}
```
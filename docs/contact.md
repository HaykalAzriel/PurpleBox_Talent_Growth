# Contact API Spec

## Create Contact API 

Endpoint : POST /api/contacts

Headers : 
- Authorization : token 

Request Body: 
```json
{
    "first_name" : "azriel",
    "last_name": "priatama", 
    "email" :"azriel@priatama.com",
    "phone" : "1234567"
}
```
Response Body Succes: 
```json
{
    "data": {
    "id" : 1,
    "first_name" : "azriel",
    "last_name": "priatama" ,
    "email" :"azriel@priatama.com",
    "phone" : "1234567"
}
}
```
Response Body Errors: 

```json
{
    "errors" : "Invalid email format"
}
```

## Update Contact API 

Endpoint : PUT /api/contact/:id

Headers : 
- Authorization : token

Request Body: 

```json
{
    "first_name" : "azriel",
    "last_name": "priatama" ,
    "email" : "azriel@priatama.com",
    "phone" : "1234567"
}
```

Response Body Succes: 

```json
{
    "data" : {
    "id" : 1,   
    "first_name" : "azriel",
    "last_name": "priatama" ,
    "email" : "azriel@priatama.com",
    "phone" : "1234567"
}
}
```

Response Body Errors:

```json
{
"errors" : "Invalid email format" 
}
```
## Get Contact API 

Endpoint : GET /api/contacts/:id

Headers : 
- Authorization : token
 
Response Body Succes: 

```json
{
    "data" : {
    "id" : 1,
    "first_name" : "azriel",
    "last_name": "priatama" ,
    "email" : "azriel@priatama.com",
    "phone" : "1234567"
}
}
```


Response Body Errors:

```json
{
    "error" : "Contact is not found"
}
```

## Search Contact API 

Endpoint : GET /api/contacts

Headers : 
- Authorization : token

Querry params: 
- name : Search by first_name or last_name, using like, optional 
- email : Search by email using like, optional 
- phone : Search by phone using like, optional 
- page : number of page, defaut 1
- size : size per page, default 10  

Response Body Succes: 
```json
{
 "data" : [
    {
    "id" : 1,    
    "first_name" : "azriel",
    "last_name": "priatama",
    "email" : "azriel@priatama.com",
    "phone" : "1234567"
},
{
    "id" : 2,    
    "first_name" : "azriel",
    "last_name": "priatama",
    "email" : "azriel@priatama.com",
    "phone" : "1234567"
}
 ],
 "paging" : [
    "page" : 1, 
    "total_page" : 3, 
    "total _item" : 30
 ]

}
```
Response Body Errors:

## Remove Contact API 

Endpoint : DELETE /api/contacts/:id

Headers : 
- Authorization : token

Response Body Succes: 

```json
{
    "data" : "OK"
}
```

Response Body Errors:

```json
{
    "error" : "contact is not found" 
}
```
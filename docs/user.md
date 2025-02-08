# User API Spec

## Register User 

Endpoint : POST /api/users

 Request Body: 
 ```json
 {"username" : "arcrezzy",
  "Password" : "kepodeh",
  "Name" : "haykal"
  }
 ```
 Response Body Success: 
 ```json
{
 "data" : {
  "username" : "arcrezzy",
  "Name" : "haykal"
  }
 }
 ```
Response Body Error:
```json
[
    {
        "errors" : "Username already registered"
    },
    {
        "errors" : "Invalid Username Format, Username must not contain special characters."
    }
]
```


## Login User 
Endpoint : POST /api/users/login

Request Body: 

```json
{
"Username" : "arcrezzy",
"password" : "kepodeh"
} 
```

Response Body Success: 

```json
{
"data" : {
    "token" : "unique-token"
}
}
```
Response Body Error:
```json
{
    "errors" : "Wrong Password or Username"
}
```

## Update User API
Endpoint : PATCH /api/users/current

Headers : 
- Authorization : token

Request Body: 
```json
{
    "name" : "arcrezzy", 
    "password" : "new password" 
}
```
Response Body Success: 
```json
{
    "data" : {
        "username" : "arcrezzy",
        "name" : "haykal"
    }
}
```

Response Body Error : 
```json
{
    "errors" : "Invalid Username Format, Username must not contain special characters."
}
```

## Get User 

Endpoint : GET /api/users/current

Headers : 
- Authorization : token

Response Body: 

```json
{
     "data ":{
        "username" : "arcrezzy" ,
        "name" : "haykal"
     }
}
```

Response Body Error: 

```json
{
"errors" : "Unauthorized"
}
```

## LogOut User API

Endpoint : DELETE/api/users/logout

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
    "errors" : "Unauthorized"
}
```
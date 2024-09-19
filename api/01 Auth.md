# POST /api/v1/auth

`auth` endpoint allows users to authenticate and obtain access to the system.
 
#### Request Body Parameters
 
- `email` (string, required): The email address of the user.
- `pwd` (string, required): The password of the user.
 
Get the token from response and use to access other APIs

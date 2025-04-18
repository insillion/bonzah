# POST /api/v1/auth

This `auth` endpoint allows users to authenticate and obtain access to the Bonzah's Insurance policy issuance system.

By default, the auth token remains valid for 15 mins (idle period). To extend this duration (for each user), kindly reach out to the admin/Bonzah.

We recommend making the auth request prior each transaction.

#### Request Body Parameters

- `email` (string, required): The email address of the user.
    
- `pwd` (string, required): The password of the user.
    

The token from this request's response is used for the subsequent APIs

Please reach out to [brandon@bonzah.com](https://mailto:brandon@bonzah.com) to obtain Testing and/or Production credentials.

**Response**:-

| Key | Description |
| --- | --- |
| status | The status of the response. 0 indicates success. |
| txt | error message |
| token | System generated token to access other APIs |
| email | Logged in user |

_**By default – Tokens are configured to be valid for 15 minute sessions. To extend this duration, kindly reach out to**_ [<i><b>brandon@bonzah.com</b></i>](https://mailto:brandon@bonzah.com)_**.**_
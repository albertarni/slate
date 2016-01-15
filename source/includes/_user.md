# User

## Login

> HTTP Request:

```http
POST /api/v1/login HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "token": "c73f1440-a3c2-11e5-ad02-bb8d25a8db36",
        "user": {
            "id": "48",
            "name": "User One",
            "company_id": "1",
            "email": "userone@test.com",
            "photo": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/48-Y8uvMEAzCiKGsqJsuWZJWJe361oe41SB.jpg"
        }
    },
    "message": null
}
```

The user can initiate a login with this request.

### HTTP Request

`POST http://{{domain}}/api/v1/user/login`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
username | string(20) | true | The username of the user which wants to login
password | string(255) | true | The password of the user which wants to login
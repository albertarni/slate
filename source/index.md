---
title: Helga API Reference

language_tabs:
  - http: HTTP


search: true
---

# Introduction

> Standard json response for API:

```json
{
  "status": 0,
  "data": [],
  "message": null
}
```

This is an API documentation for the project Helga.

In this documentation the {domain} refers for the currently used domain site link. In case of the staging, this would be: <b>url here</b> 

This means that the link to the api is: <b>url here</b>

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

`POST http://{{domain}}/api/v2/user/login`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
username | string(20) | true | The username of the user which wants to login
password | string(255) | true | The password of the user which wants to login

# Get settings

## Get settings

> HTTP Request:

```http
GET /api/v1/get-settings HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "fuel": {
            "1": "Hybride (Electro/Benzine)",
            "2": "Hybride (Electro/Diesel)",
            "3": "Benzine",
            "4": "Diesel"
        },
        "transmission": {
            "A": "messages.transmission_automatic",
            "H": "messages.transmission_manual"
        },
        "vat": {
            "MARGE": "Marge",
            "BTW": "BTW"
        },
        "countries": {
            "1": "Algeria@Algeria",
            "2": "Angola@Angola",
            "3": "Benin@Benin",
            "4": "Botswana@Botswana",
            "5": "Burkina Faso@Burkina Faso",
            "6": "Burundi@Burundi",
            "7": "Cameroon@Cameroon",
            "8": "Cape Verde@Cape Verde",
            "9": "Central African Republic@Central African Republic"
        },
        "body": {
            "1": "Convertible",
            "2": "Coupe",
            "3": "Hatchback",
            "4": "MPV"
        },
        "task_type": {
            "incoming_transport": "Incoming Transport",
            "outgoing_transport": "Outgoing Transport",
            "other": "Other"
        },
        "task_statuses": {
            "open": "Open",
            "closed": "Closed"
        },
        "edit_values": {
            "0": "0 %",
            "4": "4 %",
            "7": "7 %"
        },
        "portals": [
            {
                "id": "939",
                "name": "Speurders.nl",
                "default_type": "other",
                "short": "SPD",
                "long": "speurders"
            },
            {
                "id": "940",
                "name": "Stern",
                "default_type": "other",
                "short": "STR",
                "long": "stern"
            },
            {
                "id": "941",
                "name": "Subaru.nl",
                "default_type": "other",
                "short": "SUB",
                "long": "subaru"
            },
            {
                "id": "942",
                "name": "Supralift",
                "default_type": "other",
                "short": "SUP",
                "long": "supralift"
            }
        ],
        "color": {
            "1": "beige",
            "2": "blue",
            "3": "brown",
            "4": "cream",
            "5": "miscellaneous"
        },
        "option": {
            "1": "4x4 performance",
            "2": "Anti-lock braking system",
            "3": "Airbag(s)",
            "4": "Air-conditioning",
            "5": "Alarm system",
            "6": "Automatic",
            "7": "On-board computer",
            "8": "Central door locking",
            "9": "Cruise Control",
            "10": "El. Climate Control",
            "11": "Electric sun roof",
            "12": "Electric windows",
            "13": "Electric mirrors"
        },
        "keys": {
            "1": 1,
            "2": 2,
            "3": 3,
            "4": 4,
            "5": 5
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/get-settings`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------


## Get company settings

> HTTP Request:

```http
GET /api/v1/get-company-settings HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": {
        "departments": {
            "1": {
                "name": "super_admin",
                "employees": [
                    {
                        "55": {
                            "name": "Hans Kraaijeveld",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "46": {
                            "name": "Zoltan Nagy",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "47": {
                            "name": "Fodor Zsolt",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "48": {
                            "name": "User One",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "82": {
                            "name": "Emailer FF",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    }
                ]
            },
            "3": {
                "name": "administration",
                "employees": [
                    {
                        "60": {
                            "name": "Virginia Woolf",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "77": {
                            "name": "Test Employee",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "82": {
                            "name": "Emailer FF",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    }
                ]
            },
            "6": {
                "name": "inspection",
                "employees": [
                    {
                        "53": {
                            "name": "Jane Austen",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    },
                    {
                        "60": {
                            "name": "Virginia Woolf",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    }
                ]
            },
            "195": {
                "name": "Test Role",
                "employees": []
            },
            "196": {
                "name": "Test Role 2",
                "employees": [
                    {
                        "73": {
                            "name": "Simple One",
                            "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                        }
                    }
                ]
            },
            "197": {
                "name": "Test Role 3",
                "employees": []
            },
            "198": {
                "name": "Test Role 4",
                "employees": []
            }
        },
        "task_templates": {
            "125": "Test template it",
            "126": "Test template ot",
            "127": "Test template other",
            "128": "Test template related",
            "129": "Test template ot",
            "130": "Test template ot"
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/get-company-settings`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


# Tasks

## List all task

> HTTP Request:

```http
GET /api/v1/list-tasks HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "135",
        "138",
        "150",
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/list-tasks`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id | integer | false | 

## List my task

> HTTP Request:

```http
GET /api/v1/list-my-tasks HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "135",
        "138",
        "150",
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/list-my-tasks`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id | integer | false | 

## Get tasks

> HTTP Request:

```http
POST /api/v1/get-tasks HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        {
            "id": "194",
            "title": "jhgjg",
            "deadline": "2015-12-21",
            "is_opened": true,
            "assignee": {
                "name": "Fodor Zsolt",
                "profile_pic_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/47-GUZElmlMsZaOcq4f24Bcm3XCJlFKIY01.jpg"
            },
            "pickup_address": "",
            "delivery_address": ""
        },
        {
            "id": "240",
            "title": "arni 123",
            "deadline": "2015-12-26",
            "is_opened": true,
            "assignee": {
                "name": "Test Employee",
                "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
            },
            "pickup_address": "Fake, 374, 455455 Tg Mures 123",
            "delivery_address": "Dutch, 444, 444445 Dutch City 123"
        }
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/get-tasks`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
task_ids | array | true | Task id's

## Get task temlate detail

> HTTP Request:

```http
GET /api/v1/get-template-details/{template_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "title": "test 123",
        "description": "description text",
        "type": "",
        "assigned_employee_id": "73",
        "assigned_role_id": "3",
        "pickup_address": "",
        "delivery_address": "",
        "deadline": ""
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/get-template-details/{template_id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Show task details

> HTTP Request:

```http
GET /api/v1/task/{id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "title": "Test task",
        "description": "Test task description\n",
        "type": "incoming_transport",
        "assigned_employee_id": "47",
        "assigned_role_id": "",
        "pickup_address": "Fake, 374, 455455 Tg Mures 123",
        "delivery_address": "Dutch, 444, 444445 Dutch City 123",
        "deadline": "2015-11-30",
        "is_opened": true,
        "task_files": [
            {
                "id": "30",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/154-X8AMlCD11jIOoGdMDvjriHMe2mDl07lJ-import_car_header_template_en.csv",
                "name": "import_car_header_template_en.csv",
                "is_image": 0
            },
            {
                "id": "31",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/154-oCvkgm7JqZnbBa9P2bwie4Zc7VWDwb7R-demo-image0.jpg",
                "name": "demo-image0.jpg",
                "is_image": 1
            }
        ],
        "comments": [
            {
                "employee_name": "User One",
                "profile_pic_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/48-Y8uvMEAzCiKGsqJsuWZJWJe361oe41SB.jpg",
                "created_at": "2015-12-17",
                "comment": "korte"
            },
            {
                "employee_name": "User One",
                "profile_pic_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/48-Y8uvMEAzCiKGsqJsuWZJWJe361oe41SB.jpg",
                "created_at": "2015-12-17",
                "comment": "alma"
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/task/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Save task

> HTTP Request:

```http
POST /api/v1/task HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/task`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id | integer | true | 
title | string | true | 
description | string | true | 
type | string | false | 
assigned_employee_id | integer | true (if assigned_role_id has not been sent) | 
assigned_role_id | integer | true (if assigned_employee_id has not been sent) | 
task_files | array(FILE) | false | 
deadline | date | false | Date format (YY-MM-DD) 
pickup_address | string | false |
delivery_address | string | false | 


## Update task

> HTTP Request:

```http
PUT /api/v1/task/{id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```

Description text here.

### HTTP Request

`PUT http://{{domain}}/api/v1/task/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
title | string | true | 
description | string | true | 
is_opened | boolean | true | 
type | string | false | 
assigned_employee_id | integer | true (if assigned_role_id has not been sent) | 
assigned_role_id | integer | true (if assigned_employee_id has not been sent) | 
task_files | array(FILE) | false | 
deadline | date | false | Date format (YY-MM-DD) 
pickup_address | string | false |
delivery_address | string | false | 

## Destroy file

> HTTP Request:

```http
POST /api/v1/task-destroy-file HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/task-destroy-file`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
task_id | integer | true | 
file_id | integer | true | 

## Save comment

> HTTP Request:

```http
POST /api/v1/task-save-comment/{task_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/task-save-comment/{task_id}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
comment | string(500) | true | 

# Order

## Create order
> HTTP Request:

```http
GET /api/v1/order-create HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "22",
        "cars": [
            {
                "price_on_invoice": "5000.00",
                "order_car_id": "116",
                "car_id": "928",
                "name": "Nissan Qashqai 2.0 Tekna 4WD (5-drs SUV)",
                "extra_costs": [
                    {
                        "id": "8",
                        "created_at": "2015-12-15 09:56:39",
                        "updated_at": "2015-12-15 09:56:39",
                        "name": "alma",
                        "order_car_id": "116",
                        "price": "100.00",
                        "employee_id": "48",
                        "type": "extra_cost"
                    }
                ]
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/order-create

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## List outgoing order cars
> HTTP Request:

```http
GET /api/v1/list-outgoing-order-cars HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "928",
        "929"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/list-outgoing-order-cars

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Add car to outgoing order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/add-outgoing-car/{car_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/add-outgoing-car/{car_id}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


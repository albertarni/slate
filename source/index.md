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
                "employees": {
                    "46": {
                        "name": "Zoltan Nagy",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    },
                    "47": {
                        "name": "Fodor Zsolt",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    },
                    "48": {
                        "name": "User One",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    }
                }
            },
            "3": {
                "name": "administration",
                "employees": {
                    "60": {
                        "name": "Virginia Woolf",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    },
                    "77": {
                        "name": "Test Employee",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    },
                    "82": {
                        "name": "Emailer FF",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    }
                }
            },
            "6": {
                "name": "inspection",
                "employees": {
                    "53": {
                        "name": "Jane Austen",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    },
                    "60": {
                        "name": "Virginia Woolf",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    }
                }
            },
            "195": {
                "name": "Test Role",
                "employees": {}
            },
            "196": {
                "name": "Test Role 2",
                "employees": {
                    "73": {
                        "name": "Simple One",
                        "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png"
                    }
                }
            }
        },
        "task_templates": {
            "125": "Test template it",
            "126": "Test template ot",
            "127": "Test template other",
            "128": "Test template related",
            "129": "Test template ot",
            "130": "Test template ot",
            "131": "Test template ot"
        },
        "clients": {
            "3": {
                "name": "Hunnik Tiel B.V.",
                "address": "Simon Stevinstraat, 15, 4004 JV Tiel"
            },
            "4": {
                "name": "Garagebedrijf Kardol B.V.",
                "address": "Stephensonstraat, 21, 4004 JA Tiel"
            },
            "5": {
                "name": "Automobielbedrijf Bert Story",
                "address": "Lagelandseweg, 66, 6545 CG Nijmegen"
            }
        },
        "car_tags": {
            "32": "Nice",
            "52": "aztamindenitdekocsi",
            "53": "teszt kocsi"
        },
        "client_tags": {
            "7": "HELGA user",
            "10": "exclusieve auto's",
            "11": "vakgarage",
            "12": "export",
            "13": "oortje pool",
            "16": " cat I A",
            "17": "marktplaats",
            "20": "bloedworst",
            "31": "rommelkont",
            "48": "brand new tag",
            "49": "brand new tag",
            "68": "nice",
            "69": "test 1",
            "70": "test",
            "71": "test2",
            "72": "test 3"
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


#Cars

## List incoming cars

> HTTP Request:

```http
POST /api/v1/list-incoming-cars HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": [
        "980",
        "951",
        "950",
        "949",
        "938"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/list-incoming-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## List in stock cars

> HTTP Request:

```http
POST /api/v1/list-instock-cars HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": [
        "980",
        "951",
        "950",
        "949",
        "938"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POSt http://{{domain}}/api/v1/list-instock-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## List outgoing cars

> HTTP Request:

```http
POST /api/v1/list-outgoing-cars HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": [
        "980",
        "951",
        "950",
        "949",
        "938"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POSt http://{{domain}}/api/v1/list-outgoing-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## List archived cars

> HTTP Request:

```http
POST /api/v1/list-archive-cars HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": [
        "980",
        "951",
        "950",
        "949",
        "938"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POSt http://{{domain}}/api/v1/list-archive-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## List all cars grouped

> HTTP Request:

```http
POST /api/v1/list-all-cars-grouped HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": {
        "incoming": [
            "980",
            "951",
            "950",
            "949",
            "938"
        ],
        "stock": [
            "952",
            "929"
        ],
        "outgoing": [
            "933",
            "928"
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POSt http://{{domain}}/api/v1/list-all-cars-grouped`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## Get cars

> HTTP Request:

```http
POST /api/v1/get-cars HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": [
        {
            "id": "980",
            "name": "Aston Martin Cygnet ",
            "regplate": "O12356",
            "year_of_make": "2015-12-16",
            "mileage": "2200",
            "location_in_stock": false,
            "visible_online": true,
            "blocked": false,
            "eu_price": "0.00",
            "eu_vat_price": "0.00",
            "b2b_price": "0.00",
            "b2c_price": "0.00",
            "url": "http://www.balletmakkai.com/images/face.png",
            "can_be_added_to_order": false
        },
        {
            "id": "951",
            "name": "Skoda Fabia ",
            "regplate": "SD44AA",
            "year_of_make": "2000-07-10",
            "mileage": "545445",
            "location_in_stock": false,
            "visible_online": true,
            "blocked": false,
            "eu_price": "",
            "eu_vat_price": "",
            "b2b_price": "",
            "b2c_price": "",
            "url": "http://www.balletmakkai.com/images/face.png",
            "can_be_added_to_order": false
        }
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POSt http://{{domain}}/api/v1/get-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 
car_ids | array | true |



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
    "data": {
        "task_id": 243
    },
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
deadline | date | false | Date format (YY-MM-DD) 
pickup_address | string | false |
delivery_address | string | false | 


## Update task

> HTTP Request:

```http
POST /api/v1/task-update/{id} HTTP/1.1

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

`POST http://{{domain}}/api/v1/task-update/{id}`

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
deadline | date | false | Date format (YY-MM-DD) 
pickup_address | string | false |
delivery_address | string | false | 

## Save task file

> HTTP Request:

```http
POST /api/v1/task-save-file/{task_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "task_files": [
            {
                "id": "4",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/135-ZaB0DyMKGJGPT26ZEYlkGEO75bG4jhpS-resource-controller1.png",
                "name": "resource-controller1.png",
                "is_image": 1
            },
            {
                "id": "5",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/135-OMtq58uXAOC9QVCjB00tiBApybegFTV9-AutotelexPRODataAPI.svc.xml",
                "name": "AutotelexPRODataAPI.svc.xml",
                "is_image": 0
            },
            {
                "id": "6",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/135-eGfWJE7KyGADlOrE0Ck3CtNhHMFfAik2-req_res_DATAAPI_0900.txt",
                "name": "req_res_DATAAPI_0900.txt",
                "is_image": 0
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/task-save-file/{task_id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
task_file | FILE | true | 


## Destroy task file

> HTTP Request:

```http
POST /api/v1/task-destroy-file HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "task_files": [
            {
                "id": "37",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/240-tmuxrlqOpF7hXxL6jEJOmfqUM2avd3zg-import_car_header_template_en.csv",
                "name": "import_car_header_template_en.csv",
                "is_image": 0
            },
            {
                "id": "38",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/240-WtU30PARjn2jQSj2B81A8z8XFWxPeIK4-demo-image0.jpg",
                "name": "demo-image0.jpg",
                "is_image": 1
            },
            {
                "id": "39",
                "download_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/task-files/240-feaexzsFNYyGKWy0dKLtVBm4WmwdHWTD-vertical-wallpapers.jpg",
                "name": "vertical-wallpapers.jpg",
                "is_image": 1
            }
        ]
    },
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
    "data": {
        "comments": [
            {
                "employee_name": "Zoltan Nagy",
                "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png",
                "created_at": "2015-12-18",
                "comment": "almafa-123"
            },
            {
                "employee_name": "Zoltan Nagy",
                "profile_pic_url": "http://local.helga/uploads/employee-avatars/public/img/user-image.png",
                "created_at": "2015-12-18",
                "comment": "almafa"
            }
        ]
    },
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
        "outgoing_cars": [
            {
                "price_on_invoice": "50000.00",
                "order_car_id": "122",
                "car_id": "928",
                "name": "Nissan Qashqai 2.0 Tekna 4WD (5-drs SUV)",
                "extra_costs": [
                    {
                        "id": "9",
                        "created_at": "2015-12-17 12:19:34",
                        "updated_at": "2015-12-17 12:19:34",
                        "name": "alma",
                        "order_car_id": "122",
                        "price": "100.00",
                        "employee_id": "48",
                        "type": "extra_cost"
                    },
                    {
                        "id": "10",
                        "created_at": "2015-12-17 12:19:40",
                        "updated_at": "2015-12-17 12:19:40",
                        "name": "korte",
                        "order_car_id": "122",
                        "price": "200.00",
                        "employee_id": "48",
                        "type": "extra_cost"
                    }
                ]
            }
        ],
        "incoming_cars": [
            {
                "price_on_invoice": "10000.00",
                "order_car_id": "123",
                "car_id": "980",
                "name": "Aston Martin Cygnet ",
                "extra_costs": []
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
car_id | integer | false | 

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

## Add extra cost 
> HTTP Request:

```http
POST /api/v1/order/{order_id}/add-extra-cost' HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": {
        "extra_cost_id": 17
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/add-extra-cost`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
order_car_id | integer| true
name | string | true
price | double | true


## Update extra cost 
> HTTP Request:

```http
POST /api/v1/order/{order_id}/update-extra-cost/{extra_cost_id} HTTP/1.1
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

`POST http://{{domain}}/api/v1/order/{order_id}/update-extra-cost/{extra_cost_id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
name | string | true
price | double | true


## Add car to outgoing order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/add-outgoing-car/{car_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "22",
        "outgoing_cars": [
            {
                "price_on_invoice": "0.00",
                "order_car_id": "126",
                "car_id": "899",
                "name": "Opel Astra ",
                "extra_costs": []
            }
        ],
        "incoming_cars": [
            {
                "price_on_invoice": "10000.00",
                "order_car_id": "123",
                "car_id": "980",
                "name": "Aston Martin Cygnet ",
                "extra_costs": []
            }
        ]
    },
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
price_on_invoice | decimal | false | 

## Remove car from outgoing order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/delete-outgoing-car/{car_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "22",
        "outgoing_cars": [],
        "incoming_cars": [
            {
                "price_on_invoice": "10000.00",
                "order_car_id": "123",
                "car_id": "980",
                "name": "Aston Martin Cygnet ",
                "extra_costs": []
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/delete-outgoing-car/{car_id}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Add car to incoming order manually
> HTTP Request:

```http
POST /api/v1/order/{order_id}/add-incoming-car HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "22",
        "outgoing_cars": [
            {
                "price_on_invoice": "0.00",
                "order_car_id": "126",
                "car_id": "899",
                "name": "Opel Astra ",
                "extra_costs": []
            }
        ],
        "incoming_cars": [
            {
                "price_on_invoice": "10000.00",
                "order_car_id": "123",
                "car_id": "980",
                "name": "Aston Martin Cygnet ",
                "extra_costs": []
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/add-incoming-car

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
regplate | string | false | 
vin_number | string | false | 
brand_id | integer | true | 
model_id | integer | true | 
model_extra | string | false | 
mileage | integer | true | 
year_of_make | date | true | Date format (YY-MM-DD) 
first_nl_reg | date | false | Date format (YY-MM-DD) 
first_int_reg | date | false | Date format (YY-MM-DD) 
color_id | integer | false | 
fuel_id | integer | true | 
gearbox_type | string | false | 
pc_type | string | true | 
body_id | integer | false |
condition | string | true |   
btw | string | true | 
price_on_invoice | double | false |
price_brutto_bpm | integer | false | 
rest_bpm | integer | false | 
price_estimated_costs | double | false | 
economic_value | double | true | 

## Remove car from incoming order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/delete-incoming-car/{car_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "22",
        "outgoing_cars": [],
        "incoming_cars": [
            {
                "price_on_invoice": "10000.00",
                "order_car_id": "123",
                "car_id": "980",
                "name": "Aston Martin Cygnet ",
                "extra_costs": []
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/delete-incoming-car/{car_id}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Import Car by Reg. Plate
> HTTP Request:

```http
GET /api/v1/import-by-regplate/{regplate} HTTP/1.1

```

> Response:

```json

```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/import-by-regplate/{regplate}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Import Car by VIN number
> HTTP Request:

```http
GET /api/v1/import-by-vin/{vin} HTTP/1.1

```

> Response:

```json

```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/import-by-vin/{vin}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
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

## Get companies by partial credentials

> HTTP Request:

```http
POST /api/v1/get-companies-login' HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        {
            "id": "1",
            "name": "myCompany"
        },
        {
            "id": "2",
            "name": "yourCompany"
        }
    ],
    "message": null
}
```


### HTTP Request

`POST http://{{domain}}/api/v1/get-companies-login`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
email | string | true | The email of the user which wants to login
password | string | true | The password of the user which wants to login


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
        "token": "458cfb10-bb7b-11e5-ba6a-23acb8434708",
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

`POST http://{{domain}}/api/v1/login`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
email | string | true | The email of the user which wants to login
password | string | true | The password of the user which wants to login
company_id | integer | true | 


## Logout

> HTTP Request:

```http
POST /api/v1/logout HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```


### HTTP Request

`POST http://{{domain}}/api/v1/logout`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Forgot password

> HTTP Request:

```http
POST /api/v1/forgot-password HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": null,
    "message": null
}
```


### HTTP Request

`POST http://{{domain}}/api/v1/forgot-password`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
email | string | true | The email of the user which wants to login

## Show profile

> HTTP Request:

```http
GET /api/v1/profile HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "email": "userone@test.com",
        "firstname": "User",
        "lastname": "One1",
        "mobile_phone": "0755555555",
        "direct_phone": "0265555555",
        "photo": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/48-vWA6qmhzZOmZxcVstIxrk4tEM8MUhl6g-122x122.jpg",
        "tempdir": "5121-56a0bd5ab5a03",
        "roles": [
            {
                "id": "3",
                "name": "administration",
                "has_role": "0",
                "can_edit": true
            },
            {
                "id": "6",
                "name": "inspection",
                "has_role": "0",
                "can_edit": true
            },
            {
                "id": "5",
                "name": "repairment",
                "has_role": "0",
                "can_edit": true
            },
            {
                "id": "2",
                "name": "sales",
                "has_role": "0",
                "can_edit": true
            },
            {
                "id": "1",
                "name": "super_admin",
                "has_role": "1",
                "can_edit": false
            }
        ]
    },
    "message": null
}
```


### HTTP Request

`GET http://{{domain}}/api/v1/profile`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Upload profile picture

> HTTP Request:

```http
POST /api/v1/profile-upload-photo HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "photo": "http://local.helga/uploads/temp/5114-56a0b950a8303/20090110_vertical002.jpg"
    },
    "message": null
}
```


### HTTP Request

`POST http://{{domain}}/api/v1/profile-upload-photo`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
tempdir | string | true |
photo | FILE | true |


## Update profile

> HTTP Request:

```http
POST /api/v1/profile HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "photo": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/48-vWA6qmhzZOmZxcVstIxrk4tEM8MUhl6g.jpg"
    },
    "message": null
}
```


### HTTP Request

`POST http://{{domain}}/api/v1/profile`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
tempdir | string | true |
firstname | string | true |
lastname | string | true |
email | string | true |
roles | array(integer) | true |
mobile_phone | string | false |
direct_phone | string | false |


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
        "color": {
            "1": "beige",
            "2": "blue",
            "3": "brown",
            "4": "cream",
            "5": "miscellaneous"
        },
        "brand_models": {
            "1": {
                "name": "Mercedes-Benz",
                "models": {
                    "1": "A 45 AMG",
                    "2": "CE 230",
                    "3": "CL 320",
                    "4": "CLA 220"
                }
            },
             "51": {
                "name": "MG",
                "models": {
                    "1604": "Montego",
                    "1605": "1600",
                    "1606": "MGF",
                    "1607": "ZR",
                    "1608": "RV8",
                    "1609": "ZS",
                    "1610": "MGA",
                    "1611": "TD",
                    "1612": "ZT",
                    "1613": "MGB",
                    "1614": "TF",
                    "1615": "Midget"
                }
            },
            "58": {
                "name": "Microcar",
                "models": {
                    "1616": "MC2",
                    "1617": "DUE",
                    "1618": "Virgo",
                    "1619": "M.Go",
                    "1620": "M-8",
                    "1621": "MC1"
                }
            }
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
            "1": "1",
            "2": "2",
            "3": "3",
            "4": "4",
            "5": "5"
        },
        "car_type": {
            "E": "EU Car",
            "U": "US Car",
            "K": "Kit Car"
        },
        "pc_type": {
            "P": "Personal",
            "C": "Commercial"
        },
        "client_types": {
            "b2b": "B2B Client",
            "b2c": "B2C Client",
            "ext": "EXT Client"
        },
        "contact_positions": {
            "admin": "Admin",
            "aftersales": "Aftersales",
            "billing_admin": "Billing Admin",
            "claims": "Claims",
            "director": "Director",
            "license_admin": "License Admin",
            "owner": "Owner",
            "purchase": "Purchase",
            "sales_b2b": "Sales B2B",
            "sales_b2c": "Sales B2C",
            "workshop": "Workshop"
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
        },
        "main_portals": {
            "4096": "0800autolease.nl",
            "4117": "123Machine",
            "4264": "Audi.nl",
            "4453": "Autodata Website 2",
            "4789": "AutoTrack.be",
            "4852": "Autowereld"
        },
        "other_portals": {
            "4138": "2dehands.be",
            "4159": "2dehands.nl",
            "4180": "AD Autobedrijf",
            "4201": "Agri Trader",
            "4222": "Anamera.com",
            "4243": "AssetTradex",
            "4285": "Auto App",
            "4306": "Auto Insite",
            "4327": "Auto Trader",
            "4348": "Auto Trader (spotplaatsing)",
            "4369": "Auto- en transportwereld",
            "4390": "AutoBLOX",
            "4411": "AutoCenter.nl",
            "4432": "Autodata Website"
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
            "can_be_added_to_order": false,
            "rest_bpm": "2000"
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
            "can_be_added_to_order": false,
            "rest_bpm": ""
        }
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/get-cars`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 
car_ids | array | true |


## Show car details

> HTTP Request:

```http
GET /api/v1/car/{id} HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": {
        "id": "2",
        "regplate": "MS81UQ",
        "first_int_reg": "",
        "first_nl_reg": "",
        "mileage": "22655",
        "btw": "BTW",
        "year_of_make": "2000-10-31",
        "model_extra": "",
        "gearbox_type": "M",
        "inspected": "0",
        "nr_of_keys": "",
        "economic_value": "6000.00",
        "price_take_away": "",
        "price_brutto_bpm": "",
        "rest_bpm": "2000",
        "vin_number": "",
        "model_year": "",
        "producer_color": "",
        "pc_type": "P",
        "car_type": "",
        "is_imported": "0",
        "brand_id": "32",
        "model_id": "1146",
        "color_id": "2",
        "fuel_id": "4",
        "body_id": "3",
        "apk_date": "",
        "guarantee_end_date": "",
        "personal_tax": "",
        "original_new_price": "",
        "location_client_id": "",
        "location_address": "",
        "commercial_status": "outgoing",
        "eu_price": "",
        "eu_vat_price": "",
        "b2b_price": "",
        "b2c_price": "",
        "location_in_stock": false,
        "is_new": true,
        "blocked": false,
        "extras": [],
        "tags": [],
        "tasks": [],
        "advertising": [],
        "commercial_note": "korte",
        "commercial_note_id": "5",
        "images": {
            "image-id-1JeM3HtdyHFPgh3Y13L72ZBfGt5IjtIC.jpg": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/car_photos/1JeM3HtdyHFPgh3Y13L72ZBfGt5IjtIC.jpg"
        },
        "transactions": {
            "incoming": {
                "order_id": "2",
                "price_on_invoice": "5000.00",
                "order_creator": {
                    "name": "Fodor Zsolt",
                    "profile_pic_url": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/employee-avatars/47-GUZElmlMsZaOcq4f24Bcm3XCJlFKIY01.jpg",
                    "role": "super_admin"
                },
                "customer": {
                    "name": "Dutch Client B2C",
                    "company": "myCompany",
                    "street": "Test Street 555",
                    "post_code": "537037",
                    "city": "Test City",
                    "country": "Netherlands"
                }
            },
            "outgoing": {}
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/car/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token 

## Update car

> HTTP Request:

```http
POST /api/v1/car-update/{id} HTTP/1.1

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

`POST http://{{domain}}/api/v1/car-update/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
mileage | integer | true |
btw | string | true |
year_of_make | date | true |
pc_type | string |true |
economic_value | double | true |
brand_id | integer | true |
model_id | integer | true |
fuel_id | integer | true |
vin_number | string | false |
regplate | string | false |
model_extra | string | false |
first_int_reg | date | false |
first_nl_reg | date | false |
apk_date | date| false |
guarantee_end_date | date | false |
color_id | integer | false |
producer_color | string | false
gearbox_type | string | false |
body_id | integer | false |
inspected | boolean | false
nr_of_keys | integer | false |
personal_tax | integer | false
is_imported | boolean | false |
car_type | string | false |
economic_value | double | false |
price_brutto_bpm | double | false |
rest_bpm | double | false |
price_take_away | double | false |
original_new_price | double | false |
b2b_price | double | false |
b2c_price | double | false |
eu_price | double | false |
eu_vat_price | double | false
is_new | boolean | false
location_in_stock | boolean | false
location_client_id | integer | false
location_address | string | false
blocked | boolean | false
extras | array(integer) | false
tags | array(integer) | false
advertising | array(integer) | false

## Create car tag

> HTTP Request:

```http
POST /api/v1/car-create-tag HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "tags": [
            {
                "id": "82",
                "value": "test tag",
                "selected": false
            },
            {
                "id": "52",
                "value": "aztamindenitdekocsi",
                "selected": false
            },
            {
                "id": "53",
                "value": "teszt kocsi",
                "selected": false
            },
            {
                "id": "80",
                "value": "Nice",
                "selected": false
            },
            {
                "id": "81",
                "value": "alma",
                "selected": true
            },
            {
                "id": "32",
                "value": "Nice",
                "selected": false
            },
            {
                "id": "83",
                "value": "korte",
                "selected": false
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/car-create-tag`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id |integer | true
name | string | true


## Save car image

> HTTP Request:

```http
POST /api/v1/car-save-image HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "images": {
            "image-id-LS3aRN1wuqCgA9uxBhixM0a7tGbLaW1f.jpg": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/car_photos/LS3aRN1wuqCgA9uxBhixM0a7tGbLaW1f.jpg"
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/car-save-image`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id | integer | true |
image | FILE | true

## Destroy car image

> HTTP Request:

```http
POST /api/v1/car-destroy-image HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "images": {
            "image-id-LS3aRN1wuqCgA9uxBhixM0a7tGbLaW1f.jpg": "https://helga1.s3-eu-west-1.amazonaws.com/uploads/car_photos/LS3aRN1wuqCgA9uxBhixM0a7tGbLaW1f.jpg"
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/car-destroy-image`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
car_id | integer| true |
prefixed_image_id | string | true |


# Clients

## List all client

> HTTP Request:

```http
POST /api/v1/list-clients HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "295",
        "296",
        "297",
        "298",
        "299",
        "550"
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/list-clients`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Get clients

> HTTP Request:

```http
POST /api/v1/get-clients HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        {
            "id": "515",
            "name": "Belastingdienst Amsterdam",
            "address": "Amsterdam"
        },
        {
            "id": "516",
            "name": "UWV GAK",
            "address": "Amsterdam"
        },
        {
            "id": "517",
            "name": "Dawney",
            "address": "Seattle"
        },
        {
            "id": "514",
            "name": "TPG Post",
            "address": "Den Haag"
        },
        {
            "id": "513",
            "name": "CMK Real Estate",
            "address": "Den Haag"
        }
    ],
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/get-clients`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
client_ids | array | false |


## Show client details

> HTTP Request:

```http
GET /api/v1/get-client-details/{id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "name": "Dutch Client B2B",
        "phone": "0077965465465",
        "email": "dutch@client.com",
        "type": "b2b",
        "vat_number": "851250440B01",
        "street": "Dutch",
        "housenr": "444",
        "post_code": "444445",
        "city": "Dutch City",
        "country_id": "200",
        "contacts": [
            {
                "id": "863",
                "name": "Test Test",
                "position": "admin",
                "phone": "",
                "email": ""
            },
            {
                "id": "864",
                "name": "Test Test 2",
                "position": "director",
                "phone": "0365238451",
                "email": "test@test.com"
            },
            {
                "id": "865",
                "name": "Albert Arnold",
                "position": "director",
                "phone": "0749093680",
                "email": "albertarni@yahoo.com"
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/get-client-details/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Save client

> HTTP Request:

```http
POST /api/v1/client HTTP/1.1

```

> Request:

```json
{
  "token" : "feb72230-b90e-11e5-ba9d-c1fd2cb0eaed",
  "client" : {
    "id"	: "626",
    "name" : "Albert Arnold",
    "phone" : "0749093680",
    "email" : "albertarni@yahoo.com",
    "type" : "b2c",
    "vat_number" : "8A12314AfG",
    "country_id" : 200,
    "street" : "Test Street",
    "housenr" : "5555",
    "post_code" : "537037",
    "city" : "Tirgu Mures"
  },
  "contact" : {
    "firstname" : "Test",
    "lastname" : "Contact",
    "position" : "director",
    "phone" : "0365289410",
    "email" : "test.contact@test.com"
  } 
}
```

> Response:

```json
{
    "status": 0,
    "data": {
        "contact_id": 861
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/client`

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
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
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
        "extra_costs": [
            {
                "id": "91",
                "name": "test-updated",
                "price": "200.00"
            }
        ]
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
POST /api/v1/extra-cost-update/{id} HTTP/1.1
```

> Response:

```json
{
    "status": 0,
    "data": {
        "extra_costs": [
            {
                "id": "91",
                "name": "test-updated",
                "price": "200.00"
            }
        ]
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/extra-cost-update/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
name | string | true
price | double | true


## Add car to outgoing order
> HTTP Request:

```http
POST /api/v1/order/add-outgoing-car/{car_id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/add-outgoing-car/{car_id}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
order_id | integer | false
rest_bpm | decimal | true |
price_on_invoice | decimal | false | 
request_insurance | boolean | false |
request_credit | boolean | false |

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
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
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
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
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
btw | string | true | 
price_on_invoice | double | false |
price_brutto_bpm | integer | false | 
rest_bpm | integer | false | 
price_estimated_costs | double | false | 
economic_value | double | true | 
is_new | boolean | true |

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
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
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
{
    "status": 0,
    "data": {
        "regplate": "01RDKS",
        "vin_number": "",
        "brand_id": "35",
        "model_id": "1258",
        "model_extra": "2.0-16V Privilège Comfort",
        "mileage": "",
        "year_of_make": "2005-02-01",
        "color_id": "7",
        "fuel_id": "3",
        "gearbox_type": "M",
        "pc_type": "P",
        "body_id": "4",
        "btw": "",
        "price_brutto_bpm": 6759,
        "rest_bpm": 445,
        "price_estimated_costs": "",
        "economic_value": "",
        "price_on_invoice": "",
        "is_new": false,
        "first_int_reg": "2005-02-18",
        "first_nl_reg": "2005-02-18"
    },
    "message": null
}
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
{
    "status": 0,
    "data": {
        "regplate": "",
        "vin_number": "1G2ZG528454160048",
        "brand_id": "8",
        "model_id": "",
        "model_extra": "320d",
        "mileage": "",
        "year_of_make": "2006-05-28",
        "color_id": "",
        "fuel_id": "",
        "gearbox_type": "",
        "pc_type": "",
        "body_id": "",
        "btw": "",
        "price_brutto_bpm": "",
        "rest_bpm": "",
        "price_estimated_costs": "",
        "economic_value": "",
        "price_on_invoice": "",
        "is_new": false,
        "first_int_reg": "",
        "first_nl_reg": ""
    },
    "message": null
}
```

Description text here.

### HTTP Request

`GET http://{{domain}}/api/v1/import-by-vin/{vin}

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Add contact to order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/add-contact HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "order_id": "2449",
        "contact_id": "864",
        "client_id": "295",
        "outgoing_cars": [
            {
                "regplate": "ARNI04",
                "price_on_invoice": "50000.00",
                "btw": "BTW",
                "order_car_id": "2723",
                "car_id": "2187",
                "name": "Skoda Fabia ",
                "extra_costs": [
                    {
                        "id": "166",
                        "name": "test1",
                        "price": "100.00"
                    },
                    {
                        "id": "167",
                        "name": "test2",
                        "price": "200.00"
                    }
                ],
                "request_insurance": "0",
                "request_credit": "1"
            }
        ],
        "incoming_cars": [
            {
                "regplate": "HR01AB",
                "price_on_invoice": "50000.00",
                "btw": "MARGE",
                "order_car_id": "2725",
                "car_id": "2220",
                "name": "Alfa Romeo 146 ",
                "extra_costs": [],
                "request_insurance": "",
                "request_credit": ""
            }
        ],
        "official_note": "",
        "customer": {
            "name": "Dutch Client B2B",
            "company": "myCompany",
            "street": "Dutch 444",
            "post_code": "444445",
            "city": "Dutch City",
            "country": "Netherlands"
        }
    },
    "message": null
}
```

Description text here.

### HTTP Request

`POST http://{{domain}}/api/v1/order/{order_id}/add-contact`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
contact_id | integer| true |


## Accept order
> HTTP Request:

```http
POST /api/v1/order/{order_id}/accept HTTP/1.1

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

`POST http://{{domain}}/api/v1/order/{order_id}/accept`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
separate_invoice_incoming | boolean | false |
separate_invoice_outgoing | boolean | false |
official_note | text | false |
---
title: Henderson Oil API Reference

language_tabs:
  - http: HTTP


search: true
---


# Introduction

> Standard json response for API:

```json
{
  "status": 0,
  "data": null,
  "message": null
}
```

This is an API documentation for the project Henderson Oil.

In this documentation the {domain} refers for the currently used domain site link : <b>http://hendersonoil.web-staging.eu</b>

This means that the link to the api is: <b>http://hendersonoil.web-staging.eu/api/v1/</b>

# Settings

## Get settings

> HTTP Request:

```http
GET /api/v1/settings HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "henderson_phone_number": "8286933471",
        "delivery_times": {
            "1": "Early morning",
            "2": "Mid Morning",
            "3": "Early Afternoon",
            "4": "Afternoon",
            "5": "Early evening",
            "6": "Evening",
            "7": "Overnight",
            "8": "Anytime Day",
            "9": "Anytime Night"
        },
        "disclaimer_text": "Esse partem vidisse et mei, cu has velit vocent contentiones. No clita impedit docendi cum, viderer inermis intellegat at eum, cetero perfecto mei eu. Mea ut persius feugait, fierent delectus ad sit. Ei inani delicatissimi sed, et nominavi lobortis constituam usu. Te aeque recusabo qui, solum clita essent mel ex, partiendo definitiones at pri. Soluta discere noluisse duo ei, est no mucius viderer euripidis, et per movet molestiae laboramus. Dicant temporibus accommodare per an.",
        "brand_standards_url": "https://www.google.com"
    },
    "message": null
}
```
Get the all aplication settings.

### HTTP Request

`GET https://{{domain}}/api/v1/settings`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------



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
        "token": "cbd35d00-1769-11e6-86bf-bbd7780b7150",
        "user": {
            "id": 1,
            "name": "User One",
            "email": "userone@test.com"
        }
    },
    "message": null
}
```

The user can initiate a login with this request.

### HTTP Request

`POST https://{{domain}}/api/v1/login`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
email | string | true | The email of the user which wants to login
password | string | true | The password of the user which wants to login

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

`POST https://{{domain}}/api/v1/logout`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Forget password

> HTTP Request:

```http
POST /api/v1/reset-password HTTP/1.1

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

`POST https://{{domain}}/api/v1/reset-password`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
email | string | true | 



# Sites and Equipments

## List sites

> HTTP Request:

```http
GET /api/v1/list-sites HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9",
        "10",
        "11",
        "12",
        "13",
        "14",
        "15",
        "16",
        "17"
    ],
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/list-sites`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## List equipments

> HTTP Request:

```http
GET /api/v1/list-equipments HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9",
        "10",
        "11",
        "12",
        "13",
        "14",
        "15",
        "16",
        "17"
    ],
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/list-equipments`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token

## Get sites

> HTTP Request:

```http
POST /api/v1/get-sites HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "1": {
            "name": "Strosin, Hackett and Beatty",
            "description": "Enim qui eos quibusdam non ex eligendi reiciendis est debitis quod adipisci cumque dicta ad laborum quas quo provident id natus.",
            "price": "855",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        },
        "5": {
            "name": "Cruickshank and Sons",
            "description": "Aut vero enim dignissimos incidunt placeat ratione occaecati aliquid magni iusto quod.",
            "price": "277",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        },
        "8": {
            "name": "Kuhn Inc",
            "description": "Incidunt voluptas aut accusantium fugit magnam esse expedita culpa distinctio similique maiores expedita ea delectus.",
            "price": "253",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        }
    },
    "message": null
}
```


### HTTP Request

`POST https://{{domain}}/api/v1/get-sites`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
ids | array(integer) | false | 


## Get equipments

> HTTP Request:

```http
POST /api/v1/get-equipments HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "1": {
            "name": "Schulist-Schumm",
            "description": "Aperiam tenetur unde culpa blanditiis sapiente voluptatem consequatur quasi fugit tenetur consequatur voluptatem odio necessitatibus architecto voluptatum dolor laboriosam ea aut.",
            "price": "983",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        },
        "5": {
            "name": "Keebler, Fadel and Rowe",
            "description": "Qui omnis accusamus dignissimos dolorem qui dignissimos expedita et accusamus non quas voluptates quae sunt eius et aut aut fuga deleniti dolore.",
            "price": "1333",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        },
        "8": {
            "name": "Schneider-Wisoky",
            "description": "Occaecati est perspiciatis rerum asperiores autem voluptatem esse non dicta iste officiis nisi quo illo dolorum in consequatur quisquam ut et neque sit.",
            "price": "1284",
            "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg"
        }
    },
    "message": null
}
```


### HTTP Request

`POST https://{{domain}}/api/v1/get-equipments`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
ids | array(integer) | false | 


## Show site

> HTTP Request:

```http
GET /api/v1/site/{id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "name": "Strosin, Hackett and Beatty",
        "description": "Enim qui eos quibusdam non ex eligendi reiciendis est debitis quod adipisci cumque dicta ad laborum quas quo provident id natus.",
        "price": "855",
        "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg",
        "images": [
            "http://hendersonoil.web-staging.eu/img/default.jpeg",
            "http://hendersonoil.web-staging.eu/img/default.jpeg",
            "http://hendersonoil.web-staging.eu/img/default.jpeg"
        ],
        "contact": {
            "name": "Bert Smitham",
            "company": "Adaptive multi-state hierarchy",
            "address": "23669 Rahsaan Walk Apt. 713\nDonnellyview, OK 69683-5834",
            "phone": "861.913.6870 x911",
            "email": "bruen.leilani@barton.com"
        }
    },
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/site/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Show equipment

> HTTP Request:

```http
GET /api/v1/equipment/{id} HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "name": "Schulist-Schumm",
        "description": "Aperiam tenetur unde culpa blanditiis sapiente voluptatem consequatur quasi fugit tenetur consequatur voluptatem odio necessitatibus architecto voluptatum dolor laboriosam ea aut.",
        "price": "983",
        "image_url": "http://hendersonoil.web-staging.eu/img/default.jpeg",
        "images": [
            "http://hendersonoil.web-staging.eu/img/default.jpeg",
            "http://hendersonoil.web-staging.eu/img/default.jpeg",
            "http://hendersonoil.web-staging.eu/img/default.jpeg"
        ],
        "contact": {
            "name": "Jazmyne Howell",
            "company": "Inverse secondary projection",
            "address": "46567 Dudley Cove\nVeronaville, CA 31848",
            "phone": "(603) 752-3062",
            "email": "ross.schumm@green.com"
        }
    },
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/equipment/{id}`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


# Price Quotes, EFT's, Invoices & Credit Cards

## Get pdf list

> HTTP Request:

```http
GET /api/v1/price-quotes HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "price_quotes": {
            "1": {
                "name": "Quod aut facilis.",
                "price": "201",
                "date": "29/12/1993",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "2": {
                "name": "Commodi temporibus quam.",
                "price": "471",
                "date": "03/01/2004",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "3": {
                "name": "Recusandae iure est sed animi.",
                "price": "100",
                "date": "04/05/1989",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "4": {
                "name": "Vel vero veritatis enim.",
                "price": "102",
                "date": "02/01/1984",
                "url": "http://www.orimi.com/pdf-test.pdf"
            }
        },
        "efts": {
            "1": {
                "name": "Soluta doloremque ipsum.",
                "price": "540",
                "date": "02/04/1970",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "2": {
                "name": "Laboriosam totam vel.",
                "price": "104",
                "date": "13/10/1999",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "3": {
                "name": "Doloribus est quam.",
                "price": "154",
                "date": "16/10/2002",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "4": {
                "name": "Tenetur provident est.",
                "price": "336",
                "date": "29/03/2007",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "5": {
                "name": "Adipisci laborum ducimus molestiae.",
                "price": "557",
                "date": "15/09/1970",
                "url": "http://www.orimi.com/pdf-test.pdf"
            }
        },
        "invoices": {
            "1": {
                "name": "Itaque quod nesciunt.",
                "price": "361",
                "date": "22/04/1971",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "2": {
                "name": "Dolorem qui voluptatibus.",
                "price": "464",
                "date": "02/04/1995",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "3": {
                "name": "Odio earum rerum.",
                "price": "244",
                "date": "04/08/2015",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "4": {
                "name": "Beatae corporis qui.",
                "price": "206",
                "date": "26/05/2009",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "5": {
                "name": "Dolores similique rerum at.",
                "price": "564",
                "date": "19/04/1975",
                "url": "http://www.orimi.com/pdf-test.pdf"
            }
        },
        "credit_cards": {
            "1": {
                "name": "Nemo tenetur in.",
                "price": "296",
                "date": "23/02/1989",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "2": {
                "name": "Vero id.",
                "price": "498",
                "date": "27/05/1973",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "3": {
                "name": "Quia expedita ullam quia.",
                "price": "377",
                "date": "19/12/2001",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "4": {
                "name": "Voluptate deleniti est.",
                "price": "519",
                "date": "15/01/2011",
                "url": "http://www.orimi.com/pdf-test.pdf"
            },
            "5": {
                "name": "Animi sint voluptatem.",
                "price": "219",
                "date": "25/02/1991",
                "url": "http://www.orimi.com/pdf-test.pdf"
            }
        }
    },
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/price-quotes`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token



# Place order

## Get sites

> HTTP Request:

```http
GET /api/v1/order/get-sites HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "9": {
            "name": "Energy Mart # 1",
            "city": "Hendersonville"
        },
        "10": {
            "name": "Energy Mart # 10",
            "city": "Arden"
        },
        "11": {
            "name": "Convenience Chief",
            "city": "Cherokee"
        },
        "12": {
            "name": "SAED-1, LLC",
            "city": "Greenville"
        },
        "13": {
            "name": "Fastrac Food Mart, Inc.",
            "city": "Leicester"
        },
        "15": {
            "name": "Holiday BP",
            "city": "Sylva"
        },
        "18": {
            "name": "Quik Mart - Swannanoa",
            "city": "Swannanoa"
        }
    },
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/order/get-sites`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token


## Get order details

> HTTP Request:

```http
GET /api/v1/order HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": {
        "price_today": "1.62",
        "price_yesterday": "2.79",
        "tank_list": {
            "712": {
                "name": "7.8 E10 Regular",
                "price": "1.25 - 2.48"
            },
            "713": {
                "name": "7.8 E10 Premium",
                "price": "1.99 - 2.43"
            },
            "714": {
                "name": "Ultra Low Sulfur Diesel (<15 ppm)",
                "price": "1.13 - 2.47"
            }
        }
    },
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/order`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
site_id | integer | true |


## Submit order

> HTTP Request:

```http
POST /api/v1/order HTTP/1.1

```

> Request:

```json
{
  "token": "17b084e0-27ce-11e6-97be-15efa7e822fe",
  "delivery_time": 1,
  "delivery_date": "2016-01-01",
  "site_id" : 9,
  "order": [
    {
      "id": 33,
      "quantity": 10
    },
    {
      "id": 32,
      "quantity": 11
    }
  ]
}
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

`POST https://{{domain}}/api/v1/order`




# Brand Standards

## Get brand standards

> HTTP Request:

```http
GET /api/v1/brand-standards HTTP/1.1

```

> Response:

```json
{
    "status": 0,
    "data": [
        {
            "name": "BP",
            "image_url": "http://local.hendersonoil/img/bp.png",
            "documents": [
                {
                    "title": "placeholder",
                    "date": "19/05/2016",
                    "pdf_url": "http://local.hendersonoil/documents/brand_standards/BP/placeholder.pdf"
                }
            ]
        },
        {
            "name": "Citgo",
            "image_url": "http://local.hendersonoil/img/citgo.png",
            "documents": [
                {
                    "title": "placeholder",
                    "date": "19/05/2016",
                    "pdf_url": "http://local.hendersonoil/documents/brand_standards/Citgo/placeholder.pdf"
                }
            ]
        },
        {
            "name": "Energy Fuels",
            "image_url": "http://local.hendersonoil/img/energyfuels.png",
            "documents": [
                {
                    "title": "placeholder",
                    "date": "19/05/2016",
                    "pdf_url": "http://local.hendersonoil/documents/brand_standards/Energy Fuels/placeholder.pdf"
                }
            ]
        },
        {
            "name": "ExxonMobile",
            "image_url": "http://local.hendersonoil/img/exxonmobile.png",
            "documents": [
                {
                    "title": "placeholder",
                    "date": "19/05/2016",
                    "pdf_url": "http://local.hendersonoil/documents/brand_standards/ExxonMobile/placeholder.pdf"
                }
            ]
        },
        {
            "name": "Shell",
            "image_url": "http://local.hendersonoil/img/shell.png",
            "documents": [
                {
                    "title": "placeholder",
                    "date": "19/05/2016",
                    "pdf_url": "http://local.hendersonoil/documents/brand_standards/Shell/placeholder.pdf"
                }
            ]
        }
    ],
    "message": null
}
```


### HTTP Request

`GET https://{{domain}}/api/v1/brand-standards`

### QUERY Parameters

Parameter | Type | Required | Description
--------- | ---- | -------- | -----------
token | string | true | The authentication token
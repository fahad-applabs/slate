---
title: Positive API Reference

language_tabs:
  - shell: CURL

includes:
  - errors

search: true
---


# Introduction

Welcome to the Positive Flo API! You can use our API to access Positve flo endpoints, which can get information on various trainers, clients, schedule, appointments, billings info and invoices.

<aside class="notice">
  For the sake of example, the hostname is set as localhost:3000. Please change the hostname according to your request.
</aside>

# Trainer Authentication

## Sign in

### Logs in a user using an email/password combination.
`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>

```json
{
  "user": {
    "email": "fahad@gmail.com",
    "password": "password"
  }
}
```
> Don't forget to include Header in the API request

> The above command returns JSON structured like this:

```json
{
  "user": {
    "role": {
        "id": 1,
        "name": "Trainer"
    },
    "first_name": "fahad",
    "last_name": "idrees",
    "email": "fahad@gmail.com",
    "id": 23,
    "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
    "mobile_number": "123456789",
    "dob": null,
    "pin": "",
    "image": null,
    "phone_number": "123456789",
    "office_phone_number": "123456789",
    "created_at": "2015-03-11T07:44:18.050Z",
    "updated_at": "2015-03-31T11:07:13.034Z",
    "abn": "123456789",
    "bsb": "123456789",
    "account_number": "123456789",
    "provider": "stripe_connect",
    "uid": "acct_153dAxAhbGMKhgAs",
    "access_code": "sk_test_6MQHogdYVYvXQOa5Svkp9DSd",
    "publishable_key": "pk_test_wjs0RkJMCPLWeS3LYWF1UETk",
    "gym_name": "",
    "gym_state": "",
    "gym_location": "",
    "dashboard": null
  }
}
```

Signing in Trainer.
### HTTP Request

`POST http://localhost:3000/api/signin`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
user[email] |  | The user email of the trainer
user[password] |  | Valid password for trainer

## Registration

### Create new user on email and password.

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```json
{
  "user": {
    "user_profile_image": "Some image",
    "role": "Trainer",
    "email": "username@gmail.com",
    "password": "password",
    "password_confirmation": "password",
    "first_name": "fahad",
    "last_name": "idrees",
    "mobile_number": "123456789",
    "bsb": "123456789",
    "account_number": "123456789",
    "abn": "123456789",
    "phone_number": "123456789",
    "office_phone_number": "123456789"
  }
}
```

> The above command returns JSON structured like this:

```json
{
  "Timestamp": 1427800674.025965,
  "user":{
  "role":{
    "id": 1,
    "name": "Trainer"
  },
    "first_name": "fahad",
    "last_name": "idrees",
    "email": "username@gmail.com",
    "id": 34,
    "auth_token": "CTuBCXYFY6yoK3PnHte6",
    "mobile_number": "123456789",
    "dob": null,
    "pin": "",
    "image": null,
    "phone_number": "123456789",
    "office_phone_number": "123456789",
    "created_at": "2015-03-31T11:17:53.496Z",
    "updated_at": "2015-03-31T11:17:53.496Z",
    "abn": "123456789",
    "bsb": "123456789",
    "account_number": "123456789",
    "provider": null,
    "uid": null,
    "access_code": null,
    "publishable_key": null,
    "gym_name": "",
    "gym_state": "",
    "gym_location": "",
    "dashboard": null
  }
}
```

Registration for Trainer.
### HTTP Request

`POST http://localhost:3000/api/signup`

### Query Parameters

  Parameter | Default | Description
  --------- | ------- | -----------
  user_profile_pic |  | This key is use to hold the image data
  user[username] | | 	The user name of new user
  user[email] | |	 The users email address.
  user[password] | | The users password.
  user[password_confirmation] | | The users password confirmation.
  user[first_name] | | First name of the trainer.
  user[last_name] | | Last name of the trainer.
  user[abn] | |Abn of the trainer.
  user[mobile_number] | | Mobile Number of the trainer.
  user[bsb] | | BSB of the trainer.
  user[account_number] | | Account Number of the trainer.
  user[phone_number] | | trainer phone number
  user[office_phone_number] | | trainer phone number
  user[gym_name] | | Gym name of the trainer
  user[gym_state] | | state of trainer
  user[gym_location] | | Location of user

<aside class="notice">
  end of trainer registrations API
</aside>

## Update Trainer

### update user password or other information.

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>

> Don't forget to include Header in the API request

```json
{
  "auth_token": "CTuBCXYFY6yoK3PnHte6",
  "user_profile_pic": "",
  "trainer": {
    "first_name": "usman",
    "last_name": "ali",
    "phone_number": "123456789",
    "office_phone_number": "123456789",
    "abn": "123456789",
    "bsb": "123456789",
    "account_number": "123456789",
    "gym_state": "",
    "gym_name": "",
    "gym_location": "",
    "dashboard": {
      "expected_earning": 123,
      "week_hour": 123,
      "achieve_date": "",
      "holidays": "",
      "supplement_sell": "",
      "revenue": "",
      "average_hourly_rate": "",
      "gym_rent": "",
      "gym_phone": "",
      "clothes": ""
    },
    "address": [
      {
        "street": "multani",
        "suburb": "failsabald",
        "state": "perth",
        "postcode": "52410",
        "is_billing": true,
        "is_default": true
      },
      {
        "street": "islamabad",
        "suburb": "perth",
        "state": "perth",
        "postcode": "52410",
        "is_shipment": true,
        "is_default": true
      }
    ]
  }
}
```

> The above command returns JSON structured like this:

```json
{
    "Timestamp": 1427802342.854998,
    "user": {
        "role": {
            "id": 1,
            "name": "Trainer"
        },
        "first_name": "usman",
        "last_name": "ali",
        "email": "username@gmail.com",
        "id": 34,
        "auth_token": "CTuBCXYFY6yoK3PnHte6",
        "mobile_number": "123456789",
        "dob": null,
        "pin": "",
        "image": null,
        "phone_number": "123456789",
        "office_phone_number": "123456789",
        "created_at": "2015-03-31T11:17:53.496Z",
        "updated_at": "2015-03-31T11:45:42.556Z",
        "abn": "123456789",
        "bsb": "123456789",
        "account_number": "123456789",
        "provider": null,
        "uid": null,
        "access_code": null,
        "publishable_key": null,
        "gym_name": "",
        "gym_state": "",
        "gym_location": "",
        "dashboard": {
            "id": 1,
            "expected_earning": 123,
            "week_hour": 123,
            "achieve_date": null,
            "holidays": null,
            "supplement_sell": null,
            "revenue": null,
            "average_hourly_rate": null,
            "avg_hourly_rate": null,
            "gym_rent": null,
            "gym_phone": "",
            "clothes": "",
            "created_at": "2015-03-31T11:45:42.661Z",
            "updated_at": "2015-03-31T11:45:42.661Z"
        },
        "address": [
            {
                "id": 14,
                "street": "qwe",
                "suburb": "qwe",
                "state": "ACT",
                "postcode": "123",
                "is_billing": true,
                "created_at": "2015-04-17T12:26:22.763Z",
                "updated_at": "2015-04-17T12:26:22.763Z",
                "is_shipment": true,
                "is_default": true
            },
            {
                "id": 15,
                "street": "qwe",
                "suburb": "qwe",
                "state": "ACT",
                "postcode": "123",
                "is_billing": true,
                "created_at": "2015-04-19T06:10:56.926Z",
                "updated_at": "2015-04-19T06:10:56.926Z",
                "is_shipment": true,
                "is_default": true
            },
            {
                "id": 16,
                "street": "qwe",
                "suburb": "qwe",
                "state": "ACT",
                "postcode": "123",
                "is_billing": true,
                "created_at": "2015-04-19T06:15:44.340Z",
                "updated_at": "2015-04-19T06:15:44.340Z",
                "is_shipment": true,
                "is_default": true
            },
            {
                "id": 18,
                "street": "multani",
                "suburb": "failsabald",
                "state": "perth",
                "postcode": "52410",
                "is_billing": true,
                "created_at": "2015-03-31T11:45:42.813Z",
                "updated_at": "2015-03-31T11:45:42.813Z",
                "is_shipment": false,
                "is_default": true
            },
            {
                "id": 19,
                "street": "islamabad",
                "suburb": "perth",
                "state": "perth",
                "postcode": "52410",
                "is_billing": null,
                "created_at": "2015-03-31T11:45:42.847Z",
                "updated_at": "2015-03-31T11:45:42.847Z",
                "is_shipment": true,
                "is_default": true
            }
        ],
        "active_addresses": {
            "default_billing": 18,
            "default_shipment": 19
        }
    }
}

```

Registration for Trainer.
### HTTP Request

`POST http://localhost:3000/api/signup`

### Query Parameters

  Parameter | Default | Description
  --------- | ------- | -----------
  user_profile_pic |  | This key is use to hold the image data
  user[username] | | 	The user name of new user
  user[email] | |	 The users email address.
  user[password] | | The users password.
  user[password_confirmation] | | The users password confirmation.
  user[first_name] | | First name of the trainer.
  user[last_name] | | Last name of the trainer.
  user[abn] | |Abn of the trainer.
  user[mobile_number] | | Mobile Number of the trainer.
  user[bsb] | | BSB of the trainer.
  user[account_number] | | Account Number of the trainer.
  user[phone_number] | | trainer phone number
  user[office_phone_number] | | trainer phone number
  user[gym_name] | | Gym name of the trainer
  user[gym_state] | | state of trainer
  user[gym_location] | | Location of user

<aside class="notice">
  end of trainer registrations API
</aside>

# Trainer

## Trainer Profile

### Get all the information of the trainer

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```CURL
  GET /api/getTrainerProfile?auth_token=hgNNhJ5rNTcPrwuw9KuC
```

> The above command returns JSON structured like this:

```json
{
  "role": {
    "id": 1,
    "name": "Trainer"
  },
  "first_name": "waseem heera",
  "last_name": "idrees",
  "email": "fahad@gmail.com",
  "id": 23,
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "mobile_number": "+61412345678",
  "dob": null,
  "pin": "",
  "image": null,
  "phone_number": "+61812345678",
  "office_phone_number": "+61890988390",
  "created_at": "2015-03-11T07:44:18.050Z",
  "updated_at": "2015-04-06T10:01:20.890Z",
  "abn": "53004085616",
  "bsb": "123456789",
  "account_number": "123456789",
  "provider": "stripe_connect",
  "uid": "acct_153dAxAhbGMKhgAs",
  "access_code": "sk_test_6MQHogdYVYvXQOa5Svkp9DSd",
  "publishable_key": "pk_test_wjs0RkJMCPLWeS3LYWF1UETk",
  "gym_name": "Snap Fitness",
  "gym_state": "NT",
  "gym_location": "Darwin CBD",
  "dashboard": null,
  "active_addresses": {
    "default_billing": 24,
    "default_shipment": 30
  },
  "addresses": [
    {
      "id": 20,
      "street": "\nlahore",
      "suburb": "mm alam road",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": true,
      "user_id": 23,
      "created_at": "2015-04-06T06:18:47.541Z",
      "updated_at": "2015-04-06T06:18:47.541Z",
      "is_shipment": false,
      "is_default": true
    },
    {
      "id": 21,
      "street": "lahore",
      "suburb": "mm alam roaf",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": false,
      "user_id": 23,
      "created_at": "2015-04-06T06:18:47.575Z",
      "updated_at": "2015-04-06T06:18:47.575Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 22,
      "street": "\nlahore",
      "suburb": "mm alam road",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": true,
      "user_id": 23,
      "created_at": "2015-04-06T06:21:47.698Z",
      "updated_at": "2015-04-06T06:21:47.698Z",
      "is_shipment": false,
      "is_default": true
    },
    {
      "id": 23,
      "street": "lahore",
      "suburb": "mm alam roaf",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": false,
      "user_id": 23,
      "created_at": "2015-04-06T06:21:47.708Z",
      "updated_at": "2015-04-06T06:21:47.708Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 24,
      "street": "\nlahore",
      "suburb": "mm alam road",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": true,
      "user_id": 23,
      "created_at": "2015-04-06T06:24:30.775Z",
      "updated_at": "2015-04-06T06:24:30.775Z",
      "is_shipment": false,
      "is_default": true
    },
    {
      "id": 25,
      "street": "lahore",
      "suburb": "mm alam roaf",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": false,
      "user_id": 23,
      "created_at": "2015-04-06T06:24:30.784Z",
      "updated_at": "2015-04-06T06:24:30.784Z",
      "is_shipment": true,
      "is_default": true
    }
  ]
}

```

Trainer Profile.
### HTTP Request

`GET /api/getTrainerProfile?auth_token=hgNNhJ5rNTcPrwuw9KuC`

<aside class="notice">
  end of Trainner profile API
</aside>
## Update Trainer Profile

### Update all the information of the trainer

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
  {
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "trainer": {
    "address": [
      {
        "is_billing": "1",
        "is_default": "1",
        "is_shipment": "0",
        "postcode": "540000",
        "state": "NSW",
        "street": "\\nlahore",
        "suburb": "mm alam road"
      },
      {
        "is_billing": "0",
        "is_default": "1",
        "is_shipment": "1",
        "postcode": "540000",
        "state": "NSW",
        "street": "lahore",
        "suburb": "mm alam roaf"
      }
    ],
    "created_at": "2015-03-11T12:44:18.050+0500",
    "first_name": "waseem chandi",
    "updated_at": "2015-04-06T15:01:20.890+0500"
  }
}
```

> The above command returns JSON structured like this:

```json
{
  "role": {
    "id": 1,
    "name": "Trainer"
  },
  "first_name": "waseem chandi",
  "last_name": "idrees",
  "email": "fahad@gmail.com",
  "id": 23,
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "mobile_number": "+61412345678",
  "dob": null,
  "pin": "",
  "image": null,
  "phone_number": "+61812345678",
  "office_phone_number": "+61890988390",
  "created_at": "2015-03-11T07:44:18.050Z",
  "updated_at": "2015-04-06T10:04:44.109Z",
  "abn": "53004085616",
  "bsb": "123456789",
  "account_number": "123456789",
  "provider": "stripe_connect",
  "uid": "acct_153dAxAhbGMKhgAs",
  "access_code": "sk_test_6MQHogdYVYvXQOa5Svkp9DSd",
  "publishable_key": "pk_test_wjs0RkJMCPLWeS3LYWF1UETk",
  "gym_name": "Snap Fitness",
  "gym_state": "NT",
  "gym_location": "Darwin CBD",
  "dashboard": null,
  "address": [
    {
      "id": 14,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-17T12:26:22.763Z",
      "updated_at": "2015-04-17T12:26:22.763Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 15,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-19T06:10:56.926Z",
      "updated_at": "2015-04-19T06:10:56.926Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 16,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-19T06:15:44.340Z",
      "updated_at": "2015-04-19T06:15:44.340Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 36,
      "street": "\nlahore",
      "suburb": "mm alam road",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": true,
      "created_at": "2015-04-06T10:04:44.158Z",
      "updated_at": "2015-04-06T10:04:44.158Z",
      "is_shipment": false,
      "is_default": true
    },
    {
      "id": 37,
      "street": "lahore",
      "suburb": "mm alam roaf",
      "state": "NSW",
      "postcode": "540000",
      "is_billing": false,
      "created_at": "2015-04-06T10:04:44.189Z",
      "updated_at": "2015-04-06T10:04:44.189Z",
      "is_shipment": true,
      "is_default": true
    }
  ],
  "active_addresses": {
    "default_billing": 36,
    "default_shipment": 37
  }
}
```

Trainer Profile.
### HTTP Request

`PUT /api/updateTrainer`

<aside class="notice">
  Update Trainer Profile API
</aside>

## Update Trainer Password

### Update Password of the Trainer

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
{
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "user": {
    "current_password": "[FILTERED]",
    "email": "fahad@gmail.com",
    "password": "[FILTERED]",
    "password_confirmation": "[FILTERED]"
  }
}
```

> The above command returns JSON structured like this:

```json
{
  "role": {
    "id": 1,
    "name": "Trainer"
  },
  "first_name": "waseem chandi",
  "last_name": "idrees",
  "email": "fahad@gmail.com",
  "id": 23,
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "mobile_number": "+61412345678",
  "dob": null,
  "pin": "",
  "image": null,
  "phone_number": "+61812345678",
  "office_phone_number": "+61890988390",
  "created_at": "2015-03-11T07:44:18.050Z",
  "updated_at": "2015-04-06T10:06:50.798Z",
  "abn": "53004085616",
  "bsb": "123456789",
  "account_number": "123456789",
  "provider": "stripe_connect",
  "uid": "acct_153dAxAhbGMKhgAs",
  "access_code": "sk_test_6MQHogdYVYvXQOa5Svkp9DSd",
  "publishable_key": "pk_test_wjs0RkJMCPLWeS3LYWF1UETk",
  "gym_name": "Snap Fitness",
  "gym_state": "NT",
  "gym_location": "Darwin CBD",
  "dashboard": null
}
```

Trainer Profile.
### HTTP Request

`PUT "/api/changePassword"`

<aside class="notice">
  Update Trainer Password API
</aside>
 
#  Invoices

## Get Invoices of the Clients

### Trainer is able to get invoices of the clients

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
  {'auth_token':'hgNNhJ5rNTcPrwuw9KuC',
    'timestamp':'0'
  }
```

> The above command returns JSON structured like this:

```json
[
  {
    "amount": 24,
    "description": "2 x test run",
    "invoice_id": 151,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:10:15.088Z",
    "items": [
      {
        "id": "49",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 2,
          "purchased_at": "2015-03-12T07:02:59.450Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 12,
    "description": "1 x test run",
    "invoice_id": 152,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:13:35.102Z",
    "items": [
      {
        "id": "48",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 1,
          "purchased_at": "2015-03-12T06:49:58.089Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 12,
    "description": "1 x test run",
    "invoice_id": 153,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:13:52.442Z",
    "items": [
      {
        "id": "47",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 1,
          "purchased_at": "2015-03-12T06:48:37.956Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 12,
    "description": "1 x test run",
    "invoice_id": 154,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:17:23.865Z",
    "items": [
      {
        "id": "47",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 1,
          "purchased_at": "2015-03-12T06:48:37.956Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 12,
    "description": "1 x test run",
    "invoice_id": 155,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:19:29.249Z",
    "items": [
      {
        "id": "47",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 1,
          "purchased_at": "2015-03-12T06:48:37.956Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 44.1,
    "description": "1 x wewq , 1 x test run",
    "invoice_id": 156,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T07:24:00.910Z",
    "items": [
      {
        "id": "50",
        "data": {
          "type": "Product",
          "product_id": 1,
          "unit_price": 321,
          "title": "wewq",
          "quantity": 1,
          "purchased_at": "2015-03-12T07:22:29.627Z",
          "catgory": "booking"
        }
      },
      {
        "id": "51",
        "data": {
          "type": "Product",
          "product_id": 2,
          "unit_price": 120,
          "title": "test run",
          "quantity": 1,
          "purchased_at": "2015-03-12T07:22:29.674Z",
          "catgory": "booking"
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
    "invoice_id": 157,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T09:55:16.811Z",
    "items": [
      {
        "id": "74",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
    "invoice_id": 158,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T09:55:20.291Z",
    "items": [
      {
        "id": "75",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
    "invoice_id": 159,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T09:55:22.170Z",
    "items": [
      {
        "id": "76",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 50.0000000000001,
    "description": "3 Prepaid Sessions",
    "invoice_id": 160,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T10:07:05.647Z",
    "items": [
      {
        "id": "17",
        "data": {
          "type": "Prepaid Session",
          "prepaid_session_rate": 16.6666666666667,
          "number_of_prepaid_session": 3,
          "amount_of_pepaid_session_charged": 50.0000000000001
        }
      }
    ]
  },
  {
    "amount": 50.0000000000001,
    "description": "3 Prepaid Sessions",
    "invoice_id": 161,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-12T10:37:10.250Z",
    "items": [
      {
        "id": "17",
        "data": {
          "type": "Prepaid Session",
          "prepaid_session_rate": 16.6666666666667,
          "number_of_prepaid_session": 3,
          "amount_of_pepaid_session_charged": 50.0000000000001
        }
      }
    ]
  },
  {
    "amount": 154.5625,
    "description": "3 Prepaid Sessions",
    "invoice_id": 162,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-20T05:56:55.299Z",
    "items": [
      {
        "id": "25",
        "data": {
          "type": "Prepaid Session",
          "prepaid_session_rate": 50,
          "number_of_prepaid_session": 3,
          "amount_of_pepaid_session_charged": 154.5625
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 163,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:07:31.212Z",
    "items": [
      {
        "id": "81",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 673
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 164,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:14:20.626Z",
    "items": [
      {
        "id": "83",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 165,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:15:01.128Z",
    "items": [
      {
        "id": "81",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 505
        }
      }
    ]
  },
  {
    "amount": 60.825,
    "description": "1 x 60 min Session",
    "invoice_id": 166,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:15:17.336Z",
    "items": [
      {
        "id": "84",
        "data": {
          "type": "Session",
          "hourly_charges": 60,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 60.825,
    "description": "1 x 60 min Session",
    "invoice_id": 167,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:15:27.403Z",
    "items": [
      {
        "id": "84",
        "data": {
          "type": "Session",
          "hourly_charges": 60,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 168,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:16:24.625Z",
    "items": [
      {
        "id": "83",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 169,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:16:26.402Z",
    "items": [
      {
        "id": "81",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 337
        }
      }
    ]
  },
  {
    "amount": 60.825,
    "description": "1 x 60 min Session",
    "invoice_id": 170,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:16:28.249Z",
    "items": [
      {
        "id": "84",
        "data": {
          "type": "Session",
          "hourly_charges": 60,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 60.825,
    "description": "1 x 60 min Session",
    "invoice_id": 171,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:16:30.128Z",
    "items": [
      {
        "id": "84",
        "data": {
          "type": "Session",
          "hourly_charges": 60,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 172,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:27:06.348Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 721
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 173,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:27:31.163Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 553
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 174,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:27:38.895Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 385
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 175,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:27:52.036Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 217
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 176,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:28:52.357Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 49
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 177,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:29:04.816Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 49
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 178,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:30:58.220Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 49
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 179,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:31:59.631Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 49
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 180,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:35:19.534Z",
    "items": [
      {
        "id": "85",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 49
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 181,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:43:43.577Z",
    "items": [
      {
        "id": "87",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1585
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 182,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:44:20.350Z",
    "items": [
      {
        "id": "87",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 865
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 183,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:44:25.714Z",
    "items": [
      {
        "id": "87",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 121
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 184,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:45:03.933Z",
    "items": [
      {
        "id": "87",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 121
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 185,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:49:28.964Z",
    "items": [
      {
        "id": "88",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 8713
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 186,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:49:34.480Z",
    "items": [
      {
        "id": "88",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 8545
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 187,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:49:48.316Z",
    "items": [
      {
        "id": "88",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 8377
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 188,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:50:25.794Z",
    "items": [
      {
        "id": "88",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 8209
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 189,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:51:46.383Z",
    "items": [
      {
        "id": "88",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 8041
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 190,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-24T11:51:48.230Z",
    "items": [
      {
        "id": "89",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 1
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 191,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:25:20.747Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 192,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:35:06.436Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 193,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:36:19.342Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 194,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:36:34.225Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 195,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:36:38.795Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 196,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:36:52.311Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 197,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:37:12.233Z",
    "items": [
      {
        "id": "96",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 198,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:43:02.783Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 199,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:44:25.160Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 200,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:44:28.645Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 201,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:44:36.409Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 202,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:44:42.226Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 203,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:44:45.017Z",
    "items": [
      {
        "id": "97",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 3793
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 204,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:09.952Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 205,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:43.542Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 206,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:48.430Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 207,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:50.245Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 208,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:54.578Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 209,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T07:59:58.155Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 210,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-25T08:00:07.511Z",
    "items": [
      {
        "id": "99",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 4465
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 211,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-27T09:04:03.569Z",
    "items": [
      {
        "id": "100",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 212,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-03T09:06:24.787Z",
    "items": [
      {
        "id": "100",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 213,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-10T09:06:54.362Z",
    "items": [
      {
        "id": "100",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 214,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-17T09:07:11.770Z",
    "items": [
      {
        "id": "100",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 215,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-24T09:07:22.488Z",
    "items": [
      {
        "id": "100",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 817
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 216,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-05-01T09:46:32.878Z",
    "items": [
      {
        "id": "101",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 2977
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 217,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-06-05T09:47:32.670Z",
    "items": [
      {
        "id": "101",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 2977
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 218,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-07-03T09:47:42.022Z",
    "items": [
      {
        "id": "101",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 2977
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 219,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-07-31T09:48:44.363Z",
    "items": [
      {
        "id": "101",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 2977
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 220,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-27T10:05:21.893Z",
    "items": [
      {
        "id": "102",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 337
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 221,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-03-27T10:08:43.169Z",
    "items": [
      {
        "id": "104",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 505
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 222,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-03T10:08:51.176Z",
    "items": [
      {
        "id": "104",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 505
        }
      }
    ]
  },
  {
    "amount": 45.61875,
    "description": "1 x 60 min Session",
    "invoice_id": 223,
    "client_id": 24,
    "trainer_id": 23,
    "created_at": "2015-04-10T10:08:57.056Z",
    "items": [
      {
        "id": "104",
        "data": {
          "type": "Session",
          "hourly_charges": 45,
          "total_time": 505
        }
      }
    ]
  }
]
```

Trainer Invoices
### HTTP Request

`GET "/api/invoices.json?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=0"`

<aside class="notice">
  Get Invoices of the clients
</aside>

#Clients

## Get Clients

### Trainer is able to get info of all clients

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
  {'auth_token':'hgNNhJ5rNTcPrwuw9KuC',
    'timestamp': '1428307877.360093'
  }
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 37,
    "start_date": "2015-04-06T00:00:00.000Z",
    "default_session_duration": 0,
    "default_session_rate": 45,
    "total_number_of_sessions": 0,
    "first_name": "Ahsan  Khan",
    "last_name": "Ali",
    "email": "ahsangoogle@gmail.com",
    "active": true,
    "dob": "1990-01-03T00:00:00.000Z",
    "mobile_number": "+61400000000",
    "phone_number": "",
    "office_phone_number": "",
    "accepted_invitation": false,
    "is_supplement_only_client": false,
    "created_at": "2015-04-06T07:34:58.251Z",
    "updated_at": "2015-04-06T07:35:03.843Z",
    "duration": null,
    "user_id": 37,
    "role": "Client",
    "image": null,
    "addresses": [
      {
        "id": 30,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": false,
        "created_at": "2015-04-06T07:34:58.235Z",
        "updated_at": "2015-04-06T07:34:58.235Z",
        "is_shipment": true,
        "is_default": true
      },
      {
        "id": 31,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-06T07:34:58.242Z",
        "updated_at": "2015-04-06T07:34:58.242Z",
        "is_shipment": false,
        "is_default": true
      },
      {
        "id": 32,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": false,
        "created_at": "2015-04-06T07:39:20.566Z",
        "updated_at": "2015-04-06T07:39:20.566Z",
        "is_shipment": false,
        "is_default": true
      },
      {
        "id": 33,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-06T07:39:20.578Z",
        "updated_at": "2015-04-06T07:39:20.578Z",
        "is_shipment": false,
        "is_default": true
      },
      {
        "id": 34,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-06T09:04:10.194Z",
        "updated_at": "2015-04-06T09:04:10.194Z",
        "is_shipment": false,
        "is_default": true
      },
      {
        "id": 35,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": false,
        "created_at": "2015-04-06T09:04:10.201Z",
        "updated_at": "2015-04-06T09:04:10.201Z",
        "is_shipment": false,
        "is_default": true
      }
    ],
    "comments": [],
    "payment": {
      "id": 17,
      "card_holder_name": "John",
      "card_type": "VISA",
      "card_number": "4242",
      "security_code": "123",
      "trainer_id": null,
      "client_id": 18,
      "created_at": "2015-04-06T07:35:03.848Z",
      "updated_at": "2015-04-06T09:04:10.241Z",
      "token": "tok_15oUl3AhbGMKhgAs48BG0gJx",
      "expiry_date": "2019-12-01"
    },
    "prepaid_sessions": []
  },
  {
    "id": 31,
    "start_date": "2015-04-19T00:00:00.000Z",
    "default_session_duration": 0,
    "default_session_rate": 45,
    "total_number_of_sessions": 0,
    "first_name": "Xyz",
    "last_name": "Efghijklmnopqrstuvwxyz",
    "email": "access2coder@gmail.com",
    "active": true,
    "dob": "1990-01-03T00:00:00.000Z",
    "mobile_number": "+61400000000",
    "phone_number": "",
    "office_phone_number": "",
    "accepted_invitation": false,
    "is_supplement_only_client": false,
    "created_at": "2015-04-19T06:15:44.360Z",
    "updated_at": "2015-04-19T06:15:50.260Z",
    "duration": null,
    "user_id": 31,
    "role": "Client",
    "image": null,
    "addresses": [
      {
        "id": 16,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-19T06:15:44.340Z",
        "updated_at": "2015-04-19T06:15:44.340Z",
        "is_shipment": true,
        "is_default": true
      }
    ],
    "comments": [],
    "payment": {
      "id": 15,
      "card_holder_name": "John",
      "card_type": "VISA",
      "card_number": "4242",
      "security_code": "123",
      "trainer_id": null,
      "client_id": 15,
      "created_at": "2015-04-19T06:15:50.266Z",
      "updated_at": "2015-04-19T06:15:50.266Z",
      "token": "tok_15kqkwAhbGMKhgAsQeK6XwoX",
      "expiry_date": "2019-12-01"
    },
    "prepaid_sessions": []
  },
  {
    "id": 30,
    "start_date": "2015-04-19T00:00:00.000Z",
    "default_session_duration": 0,
    "default_session_rate": 45,
    "total_number_of_sessions": 0,
    "first_name": "Rstuvwxyz",
    "last_name": "Xyz",
    "email": "uvwxyz@gmail.com",
    "active": true,
    "dob": "1990-01-03T00:00:00.000Z",
    "mobile_number": "+61400000000",
    "phone_number": "",
    "office_phone_number": "",
    "accepted_invitation": true,
    "is_supplement_only_client": false,
    "created_at": "2015-04-17T12:26:22.800Z",
    "updated_at": "2015-04-19T06:10:57.029Z",
    "duration": null,
    "user_id": 30,
    "role": "Client",
    "image": null,
    "addresses": [
      {
        "id": 14,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-17T12:26:22.763Z",
        "updated_at": "2015-04-17T12:26:22.763Z",
        "is_shipment": true,
        "is_default": true
      },
      {
        "id": 15,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-04-19T06:10:56.926Z",
        "updated_at": "2015-04-19T06:10:56.926Z",
        "is_shipment": true,
        "is_default": true
      }
    ],
    "comments": [],
    "payment": {
      "id": 14,
      "card_holder_name": "John",
      "card_type": "VISA",
      "card_number": "4242",
      "security_code": "123",
      "trainer_id": null,
      "client_id": 14,
      "created_at": "2015-04-17T12:26:30.537Z",
      "updated_at": "2015-04-19T06:11:02.624Z",
      "token": "tok_15kqgKAhbGMKhgAskhxKgxhF",
      "expiry_date": "2019-12-01"
    },
    "prepaid_sessions": []
  },
  {
    "id": 24,
    "start_date": "2015-03-12T00:00:00.000Z",
    "default_session_duration": 60,
    "default_session_rate": 45,
    "total_number_of_sessions": 2,
    "first_name": "Fahad",
    "last_name": "Idrees",
    "email": "fahad1@gmail.com",
    "active": true,
    "dob": "1990-01-02T00:00:00.000Z",
    "mobile_number": "+923215273567",
    "phone_number": "",
    "office_phone_number": "",
    "accepted_invitation": true,
    "is_supplement_only_client": false,
    "created_at": "2015-03-12T05:17:00.735Z",
    "updated_at": "2015-04-06T09:06:01.081Z",
    "duration": null,
    "user_id": 24,
    "role": "Client",
    "image": null,
    "addresses": [
      {
        "id": 8,
        "street": "qwe",
        "suburb": "qwe",
        "state": "ACT",
        "postcode": "123",
        "is_billing": true,
        "created_at": "2015-03-12T05:17:00.631Z",
        "updated_at": "2015-03-12T05:17:00.631Z",
        "is_shipment": true,
        "is_default": true
      }
    ],
    "comments": [
      {
        "id": 1,
        "body": "dfdsfsdf",
        "commented_at": "2015-04-06T14:07:13.039z"
      }
    ],
    "payment": {
      "id": 8,
      "card_holder_name": "fdsfsdff",
      "card_type": "Master",
      "card_number": "4242",
      "security_code": "123",
      "trainer_id": null,
      "client_id": 8,
      "created_at": "2015-03-12T05:18:11.080Z",
      "updated_at": "2015-04-06T09:07:20.712Z",
      "token": "tok_15fTW8Jtw1Ms13JpfKnZV79T",
      "expiry_date": "2019-02-01"
    },
    "prepaid_sessions": [
      {
        "id": 17,
        "prepaid_session_rate": 16.6666666666667,
        "number_of_prepaid_session": 3,
        "created_at": "2015-03-12T10:04:14.909Z",
        "updated_at": "2015-03-12T10:07:05.533Z"
      },
      {
        "id": 25,
        "prepaid_session_rate": 50,
        "number_of_prepaid_session": 3,
        "created_at": "2015-03-20T05:47:41.802Z",
        "updated_at": "2015-03-20T05:56:55.058Z"
      }
    ]
  }
]
  
```

Traine able to get clients info
### HTTP Request

GET "/api/getClients?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=1428307877.360093`

<aside class="notice">
  Get Clients Info
</aside>

## Update Client Info

### Trainer is able update the client profile

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
  {
  "clients": [
    {
      "user": {
        "active": 1,
        "start_date": "12-3-2015",
        "payment": {
          "card_type": "[FILTERED]",
          "expiry_date": "[FILTERED]",
          "card_holder_name": "[FILTERED]",
          "security_code": "[FILTERED]",
          "card_number": "[FILTERED]",
          "token": "tok_15fTW8Jtw1Ms13JpfKnZV79T"
        },
        "avatar": "",
        "office_phone_number": "",
        "id": 24,
        "dob": "2-1-1990",
        "address": [],
        "mobile_number": "+923215273567",
        "last_name": "Idrees",
        "email": "fahad1@gmail.com",
        "comments": [],
        "default_session_rate": 45,
        "is_supplement_only_client": 0,
        "phone_number": "",
        "default_session_duration": 60,
        "first_name": "Fahad  King"
      }
    }
  ],
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "trainer": {}
}
```

> The above command returns JSON structured like this:

```json
{
  "role": {
    "id": 2,
    "name": "Client"
  },
  "first_name": "Fahad  King",
  "active": true,
  "last_name": "Idrees",
  "email": "fahad1@gmail.com",
  "auth_token": "6LBmCJAKy7YS6Cc5b6KC",
  "mobile_number": "+923215273567",
  "created_at": "2015-03-12T05:17:00.735Z",
  "updated_at": "2015-04-06T09:06:01.081Z",
  "dob": "1990-01-02T00:00:00.000Z",
  "image": null,
  "abn": "2015-03-12T00:00:00.000Z",
  "phone_number": "",
  "default_session_duration": 60,
  "default_session_rate": 45,
  "office_phone_number": "",
  "is_supplement_only_client": false,
  "accepted_invitation": true,
  "total_number_of_sessions": 2,
  "id": 24,
  "start_date": "2015-03-12T00:00:00.000Z",
  "trainer_id": 12,
  "payment_token": "cus_5tNMbUfDhcQ27H",
  "duration": null,
  "invoice": [
    {
      "amount": 24,
      "description": "2 x test run",
      "invoice_id": 151,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:10:15.088Z",
      "items": [
        {
          "id": "49",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 2,
            "purchased_at": "2015-03-12T07:02:59.450Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 12,
      "description": "1 x test run",
      "invoice_id": 152,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:13:35.102Z",
      "items": [
        {
          "id": "48",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 1,
            "purchased_at": "2015-03-12T06:49:58.089Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 12,
      "description": "1 x test run",
      "invoice_id": 153,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:13:52.442Z",
      "items": [
        {
          "id": "47",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 1,
            "purchased_at": "2015-03-12T06:48:37.956Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 12,
      "description": "1 x test run",
      "invoice_id": 154,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:17:23.865Z",
      "items": [
        {
          "id": "47",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 1,
            "purchased_at": "2015-03-12T06:48:37.956Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 12,
      "description": "1 x test run",
      "invoice_id": 155,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:19:29.249Z",
      "items": [
        {
          "id": "47",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 1,
            "purchased_at": "2015-03-12T06:48:37.956Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 44.1,
      "description": "1 x wewq , 1 x test run",
      "invoice_id": 156,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T07:24:00.910Z",
      "items": [
        {
          "id": "50",
          "data": {
            "type": "Product",
            "product_id": 1,
            "unit_price": 321,
            "title": "wewq",
            "quantity": 1,
            "purchased_at": "2015-03-12T07:22:29.627Z",
            "catgory": "booking"
          }
        },
        {
          "id": "51",
          "data": {
            "type": "Product",
            "product_id": 2,
            "unit_price": 120,
            "title": "test run",
            "quantity": 1,
            "purchased_at": "2015-03-12T07:22:29.674Z",
            "catgory": "booking"
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
      "invoice_id": 157,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T09:55:16.811Z",
      "items": [
        {
          "id": "74",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
      "invoice_id": 158,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T09:55:20.291Z",
      "items": [
        {
          "id": "75",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session (fahad idrees with account 123456789 should be reimbursed 42.5)",
      "invoice_id": 159,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T09:55:22.170Z",
      "items": [
        {
          "id": "76",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 50.0000000000001,
      "description": "3 Prepaid Sessions",
      "invoice_id": 160,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T10:07:05.647Z",
      "items": [
        {
          "id": "17",
          "data": {
            "type": "Prepaid Session",
            "prepaid_session_rate": 16.6666666666667,
            "number_of_prepaid_session": 3,
            "amount_of_pepaid_session_charged": 50.0000000000001
          }
        }
      ]
    },
    {
      "amount": 50.0000000000001,
      "description": "3 Prepaid Sessions",
      "invoice_id": 161,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-12T10:37:10.250Z",
      "items": [
        {
          "id": "17",
          "data": {
            "type": "Prepaid Session",
            "prepaid_session_rate": 16.6666666666667,
            "number_of_prepaid_session": 3,
            "amount_of_pepaid_session_charged": 50.0000000000001
          }
        }
      ]
    },
    {
      "amount": 154.5625,
      "description": "3 Prepaid Sessions",
      "invoice_id": 162,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-20T05:56:55.299Z",
      "items": [
        {
          "id": "25",
          "data": {
            "type": "Prepaid Session",
            "prepaid_session_rate": 50,
            "number_of_prepaid_session": 3,
            "amount_of_pepaid_session_charged": 154.5625
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 163,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:07:31.212Z",
      "items": [
        {
          "id": "81",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 673
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 164,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:14:20.626Z",
      "items": [
        {
          "id": "83",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 165,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:15:01.128Z",
      "items": [
        {
          "id": "81",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 505
          }
        }
      ]
    },
    {
      "amount": 60.825,
      "description": "1 x 60 min Session",
      "invoice_id": 166,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:15:17.336Z",
      "items": [
        {
          "id": "84",
          "data": {
            "type": "Session",
            "hourly_charges": 60,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 60.825,
      "description": "1 x 60 min Session",
      "invoice_id": 167,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:15:27.403Z",
      "items": [
        {
          "id": "84",
          "data": {
            "type": "Session",
            "hourly_charges": 60,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 168,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:16:24.625Z",
      "items": [
        {
          "id": "83",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 169,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:16:26.402Z",
      "items": [
        {
          "id": "81",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 337
          }
        }
      ]
    },
    {
      "amount": 60.825,
      "description": "1 x 60 min Session",
      "invoice_id": 170,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:16:28.249Z",
      "items": [
        {
          "id": "84",
          "data": {
            "type": "Session",
            "hourly_charges": 60,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 60.825,
      "description": "1 x 60 min Session",
      "invoice_id": 171,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:16:30.128Z",
      "items": [
        {
          "id": "84",
          "data": {
            "type": "Session",
            "hourly_charges": 60,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 172,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:27:06.348Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 721
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 173,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:27:31.163Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 553
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 174,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:27:38.895Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 385
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 175,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:27:52.036Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 217
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 176,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:28:52.357Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 49
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 177,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:29:04.816Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 49
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 178,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:30:58.220Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 49
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 179,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:31:59.631Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 49
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 180,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:35:19.534Z",
      "items": [
        {
          "id": "85",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 49
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 181,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:43:43.577Z",
      "items": [
        {
          "id": "87",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1585
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 182,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:44:20.350Z",
      "items": [
        {
          "id": "87",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 865
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 183,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:44:25.714Z",
      "items": [
        {
          "id": "87",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 121
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 184,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:45:03.933Z",
      "items": [
        {
          "id": "87",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 121
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 185,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:49:28.964Z",
      "items": [
        {
          "id": "88",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 8713
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 186,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:49:34.480Z",
      "items": [
        {
          "id": "88",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 8545
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 187,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:49:48.316Z",
      "items": [
        {
          "id": "88",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 8377
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 188,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:50:25.794Z",
      "items": [
        {
          "id": "88",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 8209
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 189,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:51:46.383Z",
      "items": [
        {
          "id": "88",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 8041
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 190,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-24T11:51:48.230Z",
      "items": [
        {
          "id": "89",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 1
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 191,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:25:20.747Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 192,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:35:06.436Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 193,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:36:19.342Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 194,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:36:34.225Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 195,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:36:38.795Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 196,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:36:52.311Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 197,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:37:12.233Z",
      "items": [
        {
          "id": "96",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 198,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:43:02.783Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 199,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:44:25.160Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 200,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:44:28.645Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 201,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:44:36.409Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 202,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:44:42.226Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 203,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:44:45.017Z",
      "items": [
        {
          "id": "97",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 3793
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 204,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:09.952Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 205,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:43.542Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 206,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:48.430Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 207,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:50.245Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 208,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:54.578Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 209,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T07:59:58.155Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 210,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-25T08:00:07.511Z",
      "items": [
        {
          "id": "99",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 4465
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 211,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-27T09:04:03.569Z",
      "items": [
        {
          "id": "100",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 212,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-03T09:06:24.787Z",
      "items": [
        {
          "id": "100",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 213,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-10T09:06:54.362Z",
      "items": [
        {
          "id": "100",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 214,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-17T09:07:11.770Z",
      "items": [
        {
          "id": "100",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 215,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-24T09:07:22.488Z",
      "items": [
        {
          "id": "100",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 817
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 216,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-05-01T09:46:32.878Z",
      "items": [
        {
          "id": "101",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 2977
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 217,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-06-05T09:47:32.670Z",
      "items": [
        {
          "id": "101",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 2977
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 218,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-07-03T09:47:42.022Z",
      "items": [
        {
          "id": "101",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 2977
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 219,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-07-31T09:48:44.363Z",
      "items": [
        {
          "id": "101",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 2977
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 220,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-27T10:05:21.893Z",
      "items": [
        {
          "id": "102",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 337
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 221,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-03-27T10:08:43.169Z",
      "items": [
        {
          "id": "104",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 505
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 222,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-03T10:08:51.176Z",
      "items": [
        {
          "id": "104",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 505
          }
        }
      ]
    },
    {
      "amount": 45.61875,
      "description": "1 x 60 min Session",
      "invoice_id": 223,
      "client_id": 24,
      "trainer_id": 23,
      "created_at": "2015-04-10T10:08:57.056Z",
      "items": [
        {
          "id": "104",
          "data": {
            "type": "Session",
            "hourly_charges": 45,
            "total_time": 505
          }
        }
      ]
    }
  ],
  "payment": {
    "id": 8,
    "card_holder_name": "fdsfsdff",
    "card_type": "Master",
    "card_number": "4242",
    "security_code": 123,
    "trainer_id": null,
    "client_id": 8,
    "created_at": "2015-03-12T05:18:11.080Z",
    "updated_at": "2015-04-06T10:14:57.391Z",
    "token": "tok_15fTW8Jtw1Ms13JpfKnZV79T",
    "expiry_date": "2019-02-01"
  },
  "consultation": [],
  "addresses": [
    {
      "id": 14,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-17T12:26:22.763Z",
      "updated_at": "2015-04-17T12:26:22.763Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 15,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-19T06:10:56.926Z",
      "updated_at": "2015-04-19T06:10:56.926Z",
      "is_shipment": true,
      "is_default": true
    },
    {
      "id": 16,
      "street": "qwe",
      "suburb": "qwe",
      "state": "ACT",
      "postcode": "123",
      "is_billing": true,
      "created_at": "2015-04-19T06:15:44.340Z",
      "updated_at": "2015-04-19T06:15:44.340Z",
      "is_shipment": true,
      "is_default": true
    }
  ],
  "comments": [],
  "prepaid_sessions": [
    {
      "id": 17,
      "prepaid_session_rate": 16.6666666666667,
      "number_of_prepaid_session": 3,
      "created_at": "2015-03-12T10:04:14.909Z",
      "updated_at": "2015-03-12T10:07:05.533Z"
    },
    {
      "id": 25,
      "prepaid_session_rate": 50,
      "number_of_prepaid_session": 3,
      "created_at": "2015-03-20T05:47:41.802Z",
      "updated_at": "2015-03-20T05:56:55.058Z"
    }
  ]
}
  
```

Traine able to update client info
### HTTP Request

`'POST "/api/updateClients"`

<aside class="notice">
  Update Client Info
</aside>

#PrepaidSession

## Create Prepaid Session

### Trainer is able create prepaid session

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
{
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "prepaid_session": {
    "client_id": "24",
    "number_of_prepaid_session": "2",
    "prepaid_session_rate": "50"
  }
}
```

> The above command returns JSON structured like this:

```json
  { 'Timestamp': '2015-04-06 16:11:49 +0500', 
    'number_of_session': 4 
  }
```

Traine able to update client info
### HTTP Request

`Started POST "/api/createPrepaidSession"`

<aside class="notice">
  Create prepaid session for Client
</aside>

#Purchase

## Create Purchase

### Trainer is able to purchase for client

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
{
  "items": [
    {
      "product_id": 1,
      "quantity": 1
    },
    {
      "product_id": 2,
      "quantity": 1
    }
  ],
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "client_id": 24,
  "purchase": {
    "client_id": 24
  }
}
```

> The above command returns JSON structured like this:

```json
{
  "id": 50,
  "trainer_id": 12,
  "client_id": 24,
  "amount": 441,
  "created_at": "2015-04-06T10:19:50.100Z",
  "updated_at": "2015-04-06T10:19:50.100Z",
  "status": null
}
```

Traine able to update client info
### HTTP Request

`POST "/api/purchases.json"`

<aside class="notice">
  End Purchases of a client
</aside>

#Appointment

## Create Event

### Trainer is create appointment for users

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
{
  "appointment": [
    {
      "event": {
        "id": 106,
        "start_date": "2015-04-12T17:25:00.000+0500",
        "clients": [
          {
            "status": "Invited",
            "client_id": 24
          }
        ],
        "duration": 60,
        "private_event": 0,
        "repeat_after": "Every Week",
        "event_type": 0,
        "event_note": "",
        "hourly_charge": 45,
        "end_date": "2015-04-12T18:25:00.000+0500",
        "trainer_id": 23,
        "all_day_event": 0
      }
    }
  ],
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC"
}
```

> The above command returns JSON structured like this:

```json
[
  {
    "event": {
      "id": 106,
      "start_date": "2015-04-12T12:25:00.000Z",
      "end_date": "2015-04-12T13:25:00.000Z",
      "all_day_event": false,
      "private_event": false,
      "hourly_charge": 45,
      "repeat_after": "Every Week",
      "trainer_id": 12,
      "created_at": "2015-04-06T07:28:41.919Z",
      "updated_at": "2015-04-06T10:22:17.363Z",
      "status": null,
      "duration": 60,
      "sms_triggered": false,
      "event_type": 0,
      "event_note": "",
      "next_recurring_date": "2015-04-12T12:25:00.000Z",
      "clients": [
        {
          "id": 138,
          "client_id": 24,
          "status": "Invited"
        }
      ]
    }
  }
]
```

Traine able to create events for client
### HTTP Request

POST "/api/updateEvents`

<aside class="notice">
  End Update/Create Event
</aside>

## Get Events

### Trainer is able to get all events

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Curl
  GET api/getEvents?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=0
```

> The above command returns JSON structured like this:

```json
{
    "Timestamp": 1428319388.788159,
    "appointment": [
        {
            "event": {
                "id": 101,
                "start_date": "2015-04-30T10:00:00.000Z",
                "end_date": "2015-09-01T11:00:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Month",
                "trainer_id": 12,
                "created_at": "2015-04-29T09:42:38.377Z",
                "updated_at": "2015-07-31T09:48:41.149Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-08-30T10:00:00.000Z",
                "clients": [
                    {
                        "id": 133,
                        "client_id": 24,
                        "status": "paid"
                    }
                ]
            }
        },
        {
            "event": {
                "id": 102,
                "start_date": "2015-03-26T10:00:00.000Z",
                "end_date": "2015-04-09T11:00:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Month",
                "trainer_id": 12,
                "created_at": "2015-03-25T09:59:15.855Z",
                "updated_at": "2015-03-27T10:05:18.774Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-04-26T10:00:00.000Z",
                "clients": [
                    {
                        "id": 134,
                        "client_id": 24,
                        "status": "paid"
                    }
                ]
            }
        },
        {
            "event": {
                "id": 103,
                "start_date": "2015-03-26T10:00:00.000Z",
                "end_date": "2015-04-09T11:00:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Month",
                "trainer_id": 12,
                "created_at": "2015-03-25T10:06:47.451Z",
                "updated_at": "2015-03-25T10:06:49.770Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-03-26T10:00:00.000Z",
                "clients": [
                    {
                        "id": 135,
                        "client_id": 24,
                        "status": "Invited"
                    }
                ]
            }
        },
        {
            "event": {
                "id": 104,
                "start_date": "2015-03-26T11:00:00.000Z",
                "end_date": "2015-04-16T12:00:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Week",
                "trainer_id": 12,
                "created_at": "2015-03-25T10:06:52.430Z",
                "updated_at": "2015-04-10T10:08:55.262Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-04-16T11:00:00.000Z",
                "clients": [
                    {
                        "id": 136,
                        "client_id": 24,
                        "status": "Confirmed"
                    }
                ]
            }
        },
        {
            "event": {
                "id": 105,
                "start_date": "2015-04-11T12:00:00.000Z",
                "end_date": "2015-04-11T13:00:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Month",
                "trainer_id": 12,
                "created_at": "2015-04-06T07:20:58.562Z",
                "updated_at": "2015-04-06T07:20:58.643Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-04-11T12:00:00.000Z",
                "clients": [
                    {
                        "id": 137,
                        "client_id": 24,
                        "status": "Invited"
                    }
                ]
            }
        },
        {
            "event": {
                "id": 106,
                "start_date": "2015-04-12T12:25:00.000Z",
                "end_date": "2015-04-12T13:25:00.000Z",
                "all_day_event": false,
                "private_event": false,
                "hourly_charge": "45",
                "repeat_after": "Every Week",
                "trainer_id": 12,
                "created_at": "2015-04-06T07:28:41.919Z",
                "updated_at": "2015-04-06T11:17:44.603Z",
                "status": null,
                "duration": 60,
                "sms_triggered": false,
                "event_type": 0,
                "event_note": "",
                "next_recurring_date": "2015-04-12T12:25:00.000Z",
                "clients": [
                    {
                        "id": 138,
                        "client_id": 24,
                        "status": "Invited"
                    }
                ]
            }
        }
    ]
}

```

Traine able to get all events
### HTTP Request

`GET api/getEvents?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=0`

<aside class="notice">
  Get Events for all clients
</aside>

#Consultations

## Get Consultations

### Trainer is able to get consultations for all clients

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Curl
  GET /api/getConsultations?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=1428321529.69337
```

> The above command returns JSON structured like this:

```json
{
    "Timestamp": 1428322389.815966,
    "consultations": [
        {
            "id": 2,
            "chest": 424,
            "hips": 4234,
            "weight": 234234,
            "waist": 44,
            "lean_body_weight": 0,
            "body_fat_weight": 0,
            "created_at": "2015-04-06T12:11:19.940Z",
            "updated_at": "2015-04-06T12:11:19.940Z",
            "image_urls": {
                "back": "https://s3.amazonaws.com/positive-flo-dev/images/6/original_png",
                "front": "https://s3.amazonaws.com/positive-flo-dev/images/4/original_png",
                "side": "https://s3.amazonaws.com/positive-flo-dev/images/5/original_png"
            },
            "measurement": null,
            "left_arm": 2342,
            "right_arm": 42342,
            "glutes": 42342,
            "left_quads": 23423,
            "right_quads": 4234233,
            "right_calf": 4234234,
            "left_calf": 4324,
            "consulted_at": "2015-04-06T12:08:17.944Z",
            "status": 2,
            "total_measurement": 8822180,
            "fat_percentage": 4,
            "comments": "",
            "client_id": 24
        }
    ]
}



```

Traine able to get all events
### HTTP Request

`GET /api/getConsultations?auth_token=hgNNhJ5rNTcPrwuw9KuC&timestamp=1428321529.69337`

<aside class="notice">
  Get Consultations for all clients
</aside>

## Create consultations

### Trainer is able to create consultations of particluar client

`Don't forget to add below Headers before API request`.

<aside class="warning">
  Accept : application/vnd.example.v1 &&
  Content-Type : application/json
</aside>


> Don't forget to include Header in the API request

```Json
  {
  "auth_token": "hgNNhJ5rNTcPrwuw9KuC",
  "consultations": [
    {
      "consultation": {
        "left_quads": 23423,
        "body_fat_weight": 0,
        "total_measurement": 8822180,
        "glutes": 42342,
        "client_id": 24,
        "right_arm": 42342,
        "lean_body_weight": 0,
        "chest": 424,
        "right_quads": 4234233,
        "fat_percentage": 4,
        "left_arm": 2342,
        "consulted_at": "2015-04-06T17:08:17.944+0500",
        "waist": 44,
        "left_calf": 4324,
        "comments": "",
        "right_calf": 4234234,
        "image_urls": {
          "back": "https://s3.amazonaws.com/positive-flo-dev/images/6/original_png",
          "side": "https://s3.amazonaws.com/positive-flo-dev/images/5/original_png",
          "front": "https://s3.amazonaws.com/positive-flo-dev/images/4/original_png"
        },
        "hips": 4234,
        "status": 2,
        "weight": 234234
      }
    }
  ]
}
```

> The above command returns JSON structured like this:

```json
{
    "Timestamp": 1428322389.815966,
    "consultations": [
        {
            "id": 2,
            "chest": 424,
            "hips": 4234,
            "weight": 234234,
            "waist": 44,
            "lean_body_weight": 0,
            "body_fat_weight": 0,
            "created_at": "2015-04-06T12:11:19.940Z",
            "updated_at": "2015-04-06T12:11:19.940Z",
            "image_urls": {
                "back": "https://s3.amazonaws.com/positive-flo-dev/images/6/original_png",
                "front": "https://s3.amazonaws.com/positive-flo-dev/images/4/original_png",
                "side": "https://s3.amazonaws.com/positive-flo-dev/images/5/original_png"
            },
            "measurement": null,
            "left_arm": 2342,
            "right_arm": 42342,
            "glutes": 42342,
            "left_quads": 23423,
            "right_quads": 4234233,
            "right_calf": 4234234,
            "left_calf": 4324,
            "consulted_at": "2015-04-06T12:08:17.944Z",
            "status": 2,
            "total_measurement": 8822180,
            "fat_percentage": 4,
            "comments": "",
            "client_id": 24
        }
    ]
}



```

Traine able to get all events
### HTTP Request

`POST "/api/updateConsultations"`

<aside class="notice">
  Create Consultations for clients
</aside>


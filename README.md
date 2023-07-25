# SwiftAccess API DOCUMENTATION

pass

The entire application is contained within the `app.rb` file.

`config.ru` is a minimal Rack configuration for unicorn.

`run-tests.sh` runs a simplistic test and generates the API
documentation below.



# REST API

The REST API to the project is described below.

## User Registraion

### Request

`POST/`

    url: https://www.swiftaccess.online/user/registration/

### Response

    HTTP/1.1 200 OK
    Status: 200 OK
    Content-Type: application/json
    []

### Body

    "username": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "email": {
        "type": "email",
        "required": true,
    },
    "password": {
        "type": "string",
        "required": true,
    },
    "Fullname": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "phone_number": {
        "type": "string",
        "required": true,
        "max_length": 15
    },
    "Address": {
        "type": "string",
        "required": true,
        "max_length": 200
    },
    "Account_reference": {
        "type": "string",
        "required": true,
        "max_length": 36
    },
    "referer_code": {
        "type": "string",
        "required": false,
        "max_length": 36
    },
    "bvn": {
        "type": "string",
        "required": true,
        "read_only": false,
        "max_length": 11
    }


## User Login

### Request

`POST`

    url https://www.swiftaccess.online/user/login/

### Response

    HTTP/1.1 201 Created
    Status: 201 Created
    Content-Type: application/json
    
### Body

    "username": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "email": {
        "type": "email",
        "required": true,
    },
    "password": {
        "type": "string",
        "required": true,
    },
    
## Password Change

### Request

`POST password/change/`

    url: https://www.swiftaccess.online/account/password/change/
### Response

   HTTP 200 OK
   Allow: POST
   Content-Type: application/json
   Vary: Accept
    
### Body

    "oldpassword": {
        "type": "string",
        "required": true,
    },
    "password1": {
        "type": "string",
        "required": true,
    },
    "password2": {
        "type": "string",
        "required": true,
    },
    
## Password Reset

### Request

`POST password/change/`

    url: https://www.swiftaccess.online/account/password/reset/
    
### Response

   HTTP 200 OK
   Allow: POST
   Content-Type: application/json
    
### Body

    "email": {
        "type": "email",
        "required": true,
    },   
    
## User Profile

### Request

`GET /profile/transactionReference`

    url: https://www.swiftaccess.online/profile/<str:transactionReference>/

### Response

   HTTP 200 OK
   Allow: GET,
   Content-Type: application/json
    
    {
      "id": integer,
      "AccBalance": string,
      "AccName": string,
      "AccNumber": string,
      "bankName": string,
      "transactionReference": string,
      "AccountReference": string
    }
 
## Data Purchase

### Request

`POST/`

    url https://www.swiftaccess.online/data_purchase/

### Response
    HTTP 200 OK
    Content-Type: application/json
    
### Body

    "mobile_number": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "network_id": {
        "type": "string",
        "required": true,
    },
    "transactionReference": {
        "type": "string",
        "required": true,
        "max_length": 36
    },
    "plan_id": {
        "type": "string",
        "required": true,
    },
    
## Airtime Topup

### Request

`POST/`

    url https://www.swiftaccess.online/airtime_topup/
    
### Body
    "mobile_number": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "network_id": {
        "type": "string",
        "required": true,
    },
    "amount": {
        "type": "string",
        "required": true,
    },
    "transactionReference": {
        "type": "string",
        "required": true,
        "max_length": 36
    },
    
### Response
    HTTP/1.1 201 
    Status: 200
    Content-Type: application/json

## Cable Subcription

### Request

`POST/`

    url https://www.swiftaccess.online/cablesub/

### Response

    Status: 200 OK
    Content-Type: application/json

### Body

    "smart_card_number": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "cableplan_id": {
        "type": "string",
        "required": true,
    },
    "cablename_id": {
        "type": "string",
        "required": true,
    },
    "transactionReference": {
        "type": "string",
        "required": true,
        "max_length": 36
    },
    


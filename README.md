# SwiftAccess API DOCUMENTATION

Data, Airtime and Utility bill payment platform.

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

### MTN 
    {
        "id": 213,
        "dataplan_id": "213",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "500.0MB",
        "plan_amount": "123"
    },
    {
        "id": 7,
        "dataplan_id": "7",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "1.0GB",
        "plan_amount": "223"
    },
    {
        "id": 8,
        "dataplan_id": "8",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "2.0GB",
        "plan_amount": "446"
    },
    {
        "id": 44,
        "dataplan_id": "44",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "3.0GB",
        "plan_amount": "669"
    },
    {
        "id": 11,
        "dataplan_id": "11",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "5.0GB",
        "plan_amount": "1115"
    },
    {
        "id": 224,
        "dataplan_id": "224",
        "network": 1,
        "plan_type": "SME",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "10.0GB",
        "plan_amount": "2230"
    },
    {
        "id": 222,
        "dataplan_id": "222",
        "network": 1,
        "plan_type": "GIFTING",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "15.0GB",
        "plan_amount": "3570"
    },
    {
        "id": 223,
        "dataplan_id": "223",
        "network": 1,
        "plan_type": "GIFTING",
        "plan_network": "MTN",
        "month_validate": "Monthly",
        "plan": "20.0GB",
        "plan_amount": "4760"
    }
    
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
        options{
        MTN ~ network_id = 1,
        GLO ~ network_id = 2,
        9MOBILE ~ network_id = 3,
        AIRTEL ~ network_id = 4
        }
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
    


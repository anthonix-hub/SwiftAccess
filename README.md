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
        "plan_id": "213",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "500.0MB",
        "plan_amount": "130"
    },
    {
        "plan_id": "7",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "1.0GB",
        "plan_amount": "229"
    },
    {
        "plan_id": "8",
        "network_id": 1,
         "plan_network": "MTN",
        "plan": "2.0GB",
        "plan_amount": "460"
    },
    {
        "plan_id": "44",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "3.0GB",    
        "plan_amount": "689"
    },
    {
        "plan_id": "11",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "5.0GB",
        "plan_amount": "1150"
    },

### GLO

    {
        "plan_id": "241",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "500.0MB",
        "plan_amount": "160"
    },
    {
        "plan_id": "236",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "1.0GB",
        "plan_amount": "260"
    },
    {
        "plan_id": "237",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "2.0GB",
        "plan_amount": "500"
    },
    {
        "plan_id": "238",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "3.0GB",
        "plan_amount": "770"
    },
    {
        "plan_id": "239",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "5.0GB",
        "plan_amount": "1250"
    },
    {
        "plan_id": "198",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "7.0GB",
        "plan_amount": "2295"
    },
    {
        "plan_id": "240",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "10.0GB",
        "plan_amount": "2550"
    },
    {
        "plan_id": "200",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "12.0GB",
        "plan_amount": "3800"
    },
    {
        "plan_id": "201",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "16.5GB",
        "plan_amount": "5000"
    },
    {
        "plan_id": "202",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "25.0GB",
        "plan_amount": "7500"
    },
    {
        "plan_id": "225",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "42.0GB",
        "plan_amount": "9500"
    },
    {
        "plan_id": "226",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "78.0GB",
        "plan_amount": "15000"
    },
    {
        "plan_id": "227",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "100.0GB",
        "plan_amount": "17000"
    },
    {
        "plan_id": "228",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "115.0GB",
        "plan_amount": "20000"
    }

### Airtel
    {
            "plan_id": "216",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "500.0MB",
            "plan_amount": "150"
        },
        {
            "plan_id": "217",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "1.0GB",
            "plan_amount": "250"
        },
        {
            "plan_id": "218",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "2.0GB",
            "plan_amount": "500"
        },
        {
            "plan_id": "145",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "1.5GB",
            "plan_amount": "990"
        },
        {
            "plan_id": "219",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "5.0GB",
            "plan_amount": "1300"
        },
        {
            "plan_id": "147",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "3.0GB",
            "plan_amount": "1600"
        },
        {
            "plan_id": "148",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "4.5GB",
            "plan_amount": "2100"
        },
        {
            "plan_id": "229",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "6.0GB",
            "plan_amount": "2500"
        },
        {
            "plan_id": "233",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "10.0GB",
            "plan_amount": "2800"
        },
        {
            "plan_id": "163",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "11.0GB",
            "plan_amount": "4000"
        },
        {
            "plan_id": "231",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "20.0GB",
            "plan_amount": "6000"
        },
        {
            "plan_id": "165",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "40.0GB",
            "plan_amount": "9650"
        },
        {
            "plan_id": "230",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "110.0GB",
            "plan_amount": "20000"
        }
    
### 9MOBILE

        {
            "plan_id": "182",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "500.0MB",
            "plan_amount": "150"
        },
        {
            "plan_id": "242",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "1.0GB",
            "plan_amount": "245"
        },
        {
            "plan_id": "183",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "1.5GB",
            "plan_amount": "300"
        },
        {
            "plan_id": "184",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "2.0GB",
            "plan_amount": "450"
        },
        {
            "plan_id": "185",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "3.0GB",
            "plan_amount": "500"
        },
        {
            "plan_id": "186",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "4.5GB",
            "plan_amount": "650"
        },
        {
            "plan_id": "243",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "5.0GB",
            "plan_amount": "1240"
        },
        {
            "plan_id": "244",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "10.0GB",
            "plan_amount": "2450"
        },
        {
            "plan_id": "187",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "11.0GB",
            "plan_amount": "2600"
        },
        {
            "plan_id": "188",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "15.0GB",
            "plan_amount": "4500"
        },
        {
            "plan_id": "245",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "20.0GB",
            "plan_amount": "5950"
        },
        {
            "plan_id": "248",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "40.0GB",
            "plan_amount": "12000"
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
    


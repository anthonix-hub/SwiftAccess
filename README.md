# SwiftAccess API DOCUMENTATION

Data, Airtime and Utility bill payment platform.

# REST API

The REST API to the project is described below.

## User Registraion

### Request

`POST/`

    url: https://www.swiftaccess.online/user/registration/

### Response
    HTTP 201 Created
    Allow: POST
    Content-Type: application/json
    Vary: Accept
    
        {
        "detail": "Verification e-mail sent."
        }



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

`POST` /user/login/

    url https://www.swiftaccess.online/user/login/

### Response
    HTTP 200 OK
    Allow: POST
    Content-Type: application/json
    
    {
    "token": String,
    "user_id": Integer,
    "Fullname": String,
    "username": String,
    "Account_reference": String,
    "phone_number": String,
    "email": String,
    "email_verified": String,
    "Account_balace": Integer,
    "Account_number": Integer,
    "Account_name": String,
    "BankName": String,
    "referal_code": String,
    "bonus_requested": True|False,
    "numbers_refered": Integer,
    "Referal_bonus": Integer,
    "payment_status": String,
    "amount_per_referer": String,
    "last_login": String,
    "date_joined": String
}


    
### Body

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
    
## Forget Password

### Request

`POST user/forgot-password/`

    url: https://www.swiftaccess.online/user/forgot-password/
    
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
 
## User Referal

### Request

`GET /user_referalView/Account_reference`

    url: https://www.swiftaccess.online/user_referalView/Account_reference/

### Response

   HTTP 200 OK
    Allow: GET, HEAD, OPTIONS
    Content-Type: application/json
    Vary: Accept
    
    {
        "code": String,
        "numbers_refered": Integer,
        "Referal_bonus": Integer,
        "payment_status": String,
        "requested_bonus": Integer,
        "total_withdrawed_bonus": Integer
    }
 
 
## Referal Bonus Request

### Request

`POST /request_RefBonus/`

    url: https://www.swiftaccess.online/request_RefBonus/

### Response

   HTTP 200 OK
    Allow: POST
    Content-Type: application/json
    Vary: Accept
    
    {
        "payment_mode_requested": bank_account| swift_account,
        "accountNumber": Interger| null,
        "Bank": String| null,
        "transactionReference": String,
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
    
<!-- 
### MTN 
    {
        "plan_id": "213",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "500.0MB",
    },
    {
        "plan_id": "7",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "1.0GB",
    },
    {
        "plan_id": "8",
        "network_id": 1,
         "plan_network": "MTN",
        "plan": "2.0GB",
    },
    {
        "plan_id": "44",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "3.0GB",   
    },
    {
        "plan_id": "11",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "5.0GB",
    },
    {
        "plan_id": "224",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "10.0GB",
    },
     {
        "plan_id": "222",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "15.0GB",
    },
     {
        "plan_id": "223",
        "network_id": 1,
        "plan_network": "MTN",
        "plan": "20.0GB",
    },
    

### GLO

    {
        "plan_id": "241",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "500.0MB",
    },
    {
        "plan_id": "236",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "1.0GB",
    },
    {
        "plan_id": "237",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "2.0GB",
    },
    {
        "plan_id": "238",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "3.0GB",
    },
    {
        "plan_id": "239",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "5.0GB",
    },
    {
        "plan_id": "198",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "7.0GB",
    },
    {
        "plan_id": "240",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "10.0GB",
    },
    {
        "plan_id": "200",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "12.0GB",
    },
    {
        "plan_id": "201",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "16.5GB",
    },
    {
        "plan_id": "202",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "25.0GB",
    },
    {
        "plan_id": "225",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "42.0GB",
    },
    {
        "plan_id": "226",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "78.0GB",
    },
    {
        "plan_id": "227",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "100.0GB",
    },
    {
        "plan_id": "228",
        "network_id": 2,
        "plan_network": "GLO",
        "plan": "115.0GB",
    }

### Airtel
    {
            "plan_id": "216",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "500.0MB",
        },
        {
            "plan_id": "217",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "1.0GB",
        },
        {
            "plan_id": "218",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "2.0GB",
        },
        {
            "plan_id": "145",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "1.5GB",
        },
        {
            "plan_id": "219",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "5.0GB",
        },
        {
            "plan_id": "147",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "3.0GB",
        },
        {
            "plan_id": "148",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "4.5GB",
        },
        {
            "plan_id": "229",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "6.0GB",
        },
        {
            "plan_id": "233",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "10.0GB",
        },
        {
            "plan_id": "163",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "11.0GB",
        },
        {
            "plan_id": "231",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "20.0GB",
        },
        {
            "plan_id": "165",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "40.0GB",
        },
        {
            "plan_id": "230",
            "network": 4,
            "plan_network": "AIRTEL",
            "plan": "110.0GB",
        }
    
### 9MOBILE

        {
            "plan_id": "182",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "500.0MB",
        },
        {
            "plan_id": "242",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "1.0GB",
        },
        {
            "plan_id": "183",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "1.5GB",
        },
        {
            "plan_id": "184",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "2.0GB",
        },
        {
            "plan_id": "185",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "3.0GB",
        },
        {
            "plan_id": "186",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "4.5GB",
        },
        {
            "plan_id": "243",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "5.0GB",
        },
        {
            "plan_id": "244",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "10.0GB",
        },
        {
            "plan_id": "187",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "11.0GB",
        },
        {
            "plan_id": "188",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "15.0GB",
        },
        {
            "plan_id": "245",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "20.0GB",
        },
        {
            "plan_id": "248",
            "network": 3,
            "plan_network": "9MOBILE",
            "plan": "40.0GB",
        }
-->
## Data Price List

### Request

`GET/` dataprice/

    url: https://www.swiftaccess.online/dataprice/

### Response
 
    HTTP 200 OK
    Allow: GET, HEAD, OPTIONS
    Content-Type: application/json
    Vary: Accept
### Return:

    {
        "MTN": [
            {
                "id": 1,
                "plan_id": 213,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "500.0MB",
                "price": 130
            },
            {
                "id": 2,
                "plan_id": 7,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "1.0GB",
                "price": 229
            },
            {
                "id": 3,
                "plan_id": 8,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "2.0GB",
                "price": 460
            },
            {
                "id": 4,
                "plan_id": 44,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "3.0GB",
                "price": 689
            },
            {
                "id": 5,
                "plan_id": 11,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "5.0GB",
                "price": 1150
            },
            {
                "id": 6,
                "plan_id": 224,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "10.0GB",
                "price": 2290
            },
            {
                "id": 7,
                "plan_id": 222,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "15.0GB",
                "price": 3865
            },
            {
                "id": 8,
                "plan_id": 223,
                "network_id": 1,
                "plan_network": "MTN",
                "plan": "20.0GB",
                "price": 4200
            }
        ],
        "GLO": [
            {
                "id": 1,
                "plan_id": 241,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "500.0MB",
                "price": 160
            },
            {
                "id": 2,
                "plan_id": 236,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "1.0GB",
                "price": 260
            },
            {
                "id": 3,
                "plan_id": 237,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "2.0GB",
                "price": 50
            },
            {
                "id": 4,
                "plan_id": 238,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "3.0GB",
                "price": 770
            },
            {
                "id": 5,
                "plan_id": 239,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "5.0GB",
                "price": 1250
            },
            {
                "id": 6,
                "plan_id": 198,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "7.0GB",
                "price": 2295
            },
            {
                "id": 7,
                "plan_id": 240,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "10.0GB",
                "price": 2550
            },
            {
                "id": 8,
                "plan_id": 200,
                "network_id": 1,
                "plan_network": "GLO",
                "plan": "12.0GB",
                "price": 3800
            },
            {
                "id": 9,
                "plan_id": 201,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "16.5GB",
                "price": 5000
            },
            {
                "id": 10,
                "plan_id": 202,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "25.0GB",
                "price": 7500
            },
            {
                "id": 11,
                "plan_id": 225,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "42.0GB",
                "price": 9500
            },
            {
                "id": 12,
                "plan_id": 226,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "78.0GB",
                "price": 15000
            },
            {
                "id": 13,
                "plan_id": 227,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "100.0GB",
                "price": 17000
            },
            {
                "id": 14,
                "plan_id": 228,
                "network_id": 2,
                "plan_network": "GLO",
                "plan": "115.0GB",
                "price": 20000
            }
        ],
        "Airtel": [
            {
                "id": 1,
                "plan_id": 216,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "500.0MB",
                "price": 150
            },
            {
                "id": 2,
                "plan_id": 217,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "1.0GB",
                "price": 250
            },
            {
                "id": 3,
                "plan_id": 218,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "2.0GB",
                "price": 990
            },
            {
                "id": 4,
                "plan_id": 145,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "1.5GB",
                "price": 500
            },
            {
                "id": 5,
                "plan_id": 219,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "5.0GB",
                "price": 1600
            },
            {
                "id": 6,
                "plan_id": 147,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "3.0GB",
                "price": 1300
            },
            {
                "id": 7,
                "plan_id": 148,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "4.5GB",
                "price": 2100
            },
            {
                "id": 8,
                "plan_id": 229,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "6.0GB",
                "price": 2500
            },
            {
                "id": 9,
                "plan_id": 233,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "10.0GB",
                "price": 2800
            },
            {
                "id": 10,
                "plan_id": 163,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "11.0GB",
                "price": 4000
            },
            {
                "id": 11,
                "plan_id": 231,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "20.0GB",
                "price": 6000
            },
            {
                "id": 12,
                "plan_id": 165,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "40.0GB",
                "price": 9650
            },
            {
                "id": 13,
                "plan_id": 230,
                "network_id": 4,
                "plan_network": "AIRTEL",
                "plan": "110.0GB",
                "price": 20000
            }
        ],
        "9Mobile": [
            {
                "id": 1,
                "plan_id": 182,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "500.0MB",
                "price": 150
            },
            {
                "id": 2,
                "plan_id": 242,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "1.0GB",
                "price": 245
            },
            {
                "id": 3,
                "plan_id": 183,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "1.5GB",
                "price": 300
            },
            {
                "id": 4,
                "plan_id": 184,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "2.0GB",
                "price": 450
            },
            {
                "id": 6,
                "plan_id": 185,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "3.0GB",
                "price": 500
            },
            {
                "id": 7,
                "plan_id": 186,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "4.5GB",
                "price": 650
            },
            {
                "id": 8,
                "plan_id": 243,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "5.0GB",
                "price": 1240
            },
            {
                "id": 9,
                "plan_id": 244,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "10.0GB",
                "price": 2450
            },
            {
                "id": 10,
                "plan_id": 187,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "11.0GB",
                "price": 2600
            },
            {
                "id": 11,
                "plan_id": 188,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "15.0GB",
                "price": 4500
            },
            {
                "id": 12,
                "plan_id": 245,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "20.0GB",
                "price": 5950
            },
            {
                "id": 13,
                "plan_id": 248,
                "network_id": 3,
                "plan_network": "9MOBILE",
                "plan": "40.0GB",
                "price": 12000
            }
        ]
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

## Utility_bill Payment

### Request

`POST/`

    url https://www.swiftaccess.online/Utility_bill/
    
### Body
    "meter_number": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "disco": {
        "type": "string",
        "required": true,
        "max_length": 50
    },
    "MeterType": {
        "type": "string",
        "required": true,
        options{
        PREPAID: 1,
        POSTPAID: 2 
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
    
### Disco names
    1 	Ikeja Electric
    2 	Eko Electric
    3 	Abuja Electric
    4 	Kano Electric
    5 	Enugu Electric
    6 	Port Harcourt Electric
    7 	Ibadan Electric
    8 	Kaduna Electric
    9 	Jos Electric
    10 	Benin Electric
    11 	Yola Electric


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
    
## Cable IUC Validation

### Request

`GET/`

    url https://myrechargeup.com/api/validateiuc?smart_card_number=iuc&cablename=id

### Response

    Status: 200 OK
    Content-Type: application/json
    
'Example' 
    https://myrechargeup.com/api/validateiuc?smart_card_number=4613561372&cablename=GOTV
    https://myrechargeup.com/api/validateiuc?smart_card_number=02110473994&cablename=STARTIMES

### Query Params

    "smart_card_number": {
        "type": "Integer",
        "required": true,
        "max_length": 50
    },
    "cablename": {
        "type": "string",
        "required": true,
    },
    
## Cable Price List

### Request

`GET/`

    url https://www.swiftaccess.online/cableprice/

### Response

    HTTP 200 OK
    Allow: GET, HEAD, OPTIONS
    Content-Type: application/json
    Vary: Accept
### Return 
     {
        "GOTV": [
            {
                "id": 1,
                "cableplan_id": 34,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Smallie - Monthly",
                "plan_amount": 1100
            },
            {
                "id": 2,
                "cableplan_id": 16,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Jinja",
                "plan_amount": 2250
            },
            {
                "id": 3,
                "cableplan_id": 18,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Smallie",
                "plan_amount": 2240
            },
            {
                "id": 4,
                "cableplan_id": 35,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Smallie - Quarterly",
                "plan_amount": 2400
            },
            {
                "id": 5,
                "cableplan_id": 17,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Jolli",
                "plan_amount": 3300
            },
            {
                "id": 6,
                "cableplan_id": 2,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Max",
                "plan_amount": 4850
            },
            {
                "id": 7,
                "cableplan_id": 47,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "Gotv-supa-6400-monthly",
                "plan_amount": 6400
            },
            {
                "id": 8,
                "cableplan_id": 36,
                "cablename_id": 1,
                "cable": "GOTV",
                "package": "GOtv Smallie - Yearly",
                "plan_amount": 7000
            }
        ],
        "DSTV": [
            {
                "id": 1,
                "cableplan_id": 21,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Great Wall Standalone",
                "plan_amount": 2050
            },
            {
                "id": 2,
                "cableplan_id": 20,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Padi",
                "plan_amount": 2500
            },
            {
                "id": 3,
                "cableplan_id": 33,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "ExtraView Access",
                "plan_amount": 2900
            },
            {
                "id": 4,
                "cableplan_id": 32,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv HDPVR Access Service",
                "plan_amount": 2900
            },
            {
                "id": 5,
                "cableplan_id": 6,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Yanga",
                "plan_amount": 3500
            },
            {
                "id": 6,
                "cableplan_id": 27,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Yanga + ExtraView",
                "plan_amount": 5065
            },
            {
                "id": 7,
                "cableplan_id": 28,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Padi + ExtraView",
                "plan_amount": 5650
            },
            {
                "id": 8,
                "cableplan_id": 19,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Confam",
                "plan_amount": 6200
            },
            {
                "id": 9,
                "cableplan_id": 23,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Asia",
                "plan_amount": 7100
            },
            {
                "id": 10,
                "cableplan_id": 26,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Confam + ExtraView",
                "plan_amount": 8300
            },
            {
                "id": 11,
                "cableplan_id": 29,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Compact + Extra View",
                "plan_amount": 10400
            },
            {
                "id": 12,
                "cableplan_id": 7,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Compact",
                "plan_amount": 10500
            },
            {
                "id": 13,
                "cableplan_id": 8,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Compact Plus",
                "plan_amount": 16600
            },
            {
                "id": 14,
                "cableplan_id": 31,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Compact Plus - Extra View",
                "plan_amount": 20000
            },
            {
                "id": 15,
                "cableplan_id": 5,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "Asian Bouqet",
                "plan_amount": 20295
            },
            {
                "id": 16,
                "cableplan_id": 25,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Premium Asia",
                "plan_amount": 23500
            },
            {
                "id": 17,
                "cableplan_id": 30,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Premium + Extra View",
                "plan_amount": 23900
            },
            {
                "id": 18,
                "cableplan_id": 9,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Premium",
                "plan_amount": 24500
            },
            {
                "id": 19,
                "cableplan_id": 24,
                "cablename_id": 2,
                "cable": "DSTV",
                "package": "DStv Premium French",
                "plan_amount": 29300
            }
        ],
        "STARTIME": [
            {
                "id": 1,
                "cableplan_id": 42,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Nova - 1 Day",
                "plan_amount": 100
            },
            {
                "id": 2,
                "cableplan_id": 43,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Basic - 1 Day",
                "plan_amount": 200
            },
            {
                "id": 3,
                "cableplan_id": 44,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Smart - 1 Day",
                "plan_amount": 250
            },
            {
                "id": 4,
                "cableplan_id": 37,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Nova - 1 Week",
                "plan_amount": 300
            },
            {
                "id": 5,
                "cableplan_id": 45,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Classic - 1 Day",
                "plan_amount": 320
            },
            {
                "id": 6,
                "cableplan_id": 46,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Super - 1 Day",
                "plan_amount": 500
            },
            {
                "id": 7,
                "cableplan_id": 38,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Basic - 1 Week",
                "plan_amount": 600
            },
            {
                "id": 8,
                "cableplan_id": 39,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Smart - 1 Week",
                "plan_amount": 900
            },
            {
                "id": 9,
                "cableplan_id": 14,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Nova - 1 Month",
                "plan_amount": 1200
            },
            {
                "id": 10,
                "cableplan_id": 40,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Classic 1 Week",
                "plan_amount": 1200
            },
            {
                "id": 11,
                "cableplan_id": 41,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Super - 1 Week",
                "plan_amount": 1800
            },
            {
                "id": 12,
                "cableplan_id": 12,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Basic - 1 Month",
                "plan_amount": 2100
            },
            {
                "id": 13,
                "cableplan_id": 13,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Smart - 1 Month",
                "plan_amount": 2800
            },
            {
                "id": 14,
                "cableplan_id": 11,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Classic - 1 Month",
                "plan_amount": 3100
            },
            {
                "id": 15,
                "cableplan_id": 15,
                "cablename_id": 3,
                "cable": "STARTIME",
                "package": "Super - 1 Month",
                "plan_amount": 5300
            }
        ]
    }

## Airtime Purchase History

### Request

`GET /AirtimeHistory/transactionReference`

    url: https://www.swiftaccess.online/AirtimeHistory/<str:transactionReference>/

### Response

   HTTP 200 OK
   Allow: GET,
   Content-Type: application/json
    
       {
            "id": Integer,
            "id_value": String,
            "airtime_type": String,
            "ident": String,
            "network": String,
            "paid_amount": Integer,
            "mobile_number": String,
            "amount": Integer,
            "plan_network": String,
            "Status": String,
            "create_date": String,
            "transactionReference": String
        }

## Data Purchase History

### Request

`GET /DataHistory/transactionReference`

    url: https://www.swiftaccess.online/DataHistory/<str:transactionReference>/

### Response

   HTTP 200 OK
   Allow: GET,
   Content-Type: application/json
    
       {
            "id": Integer,
            "network": Integer,
            "mobile_number": String,
            "plan": String,
            "amount": String,
            "transactionReference": String,
            "Status": String,
            "plan_network": String,
            "create_date": String,
            "plan_name": String,
            "ident": String,
            "id_value": String
        }

## Cable Purchase History

### Request

`GET /CableHistory/transactionReference`

    url: https://www.swiftaccess.online/CableHistory/<str:transactionReference>/

### Response

   HTTP 200 OK
   Allow: GET,
   Content-Type: application/json

    {
        "id": Integer, 
        "ident": String, 
        "cablename": Integer, 
        "cableplan": Integer, 
        "package": String, 
        "plan_amount": String, 
        "paid_amount": Integer, 
        "balance_before": String, 
        "balance_after": String, 
        "smart_card_number": String, 
        "Status":String, 
        "create_date": String, 
        "customer_name": String
    }
      
## Electric Bill History

### Request

`GET /Electric_billHistory/transactionReference`

    url: https://www.swiftaccess.online/Electric_billHistory/<str:transactionReference>/

### Response

   HTTP 200 OK
   Allow: GET,
   Content-Type: application/json
    
      

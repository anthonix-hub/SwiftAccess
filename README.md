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
    "key": string
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

`POST` /user/login/

    url https://www.swiftaccess.online/user/login/

### Response

    HTTP 200 OK
    Allow: POST, OPTIONS
    Content-Type: application/json
    Vary: Accept
    
    {
        "refresh": string,
        "access": string
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
        "id": 1,
        "MTN_500MB_price": integer,
        "MTN_1GB_price": integer,
        "MTN_2GB_price": integer,
        "MTN_3GB_price": integer,
        "MTN_5GB_price": integer,
        "MTN_10GB_price": integer,
        "MTN_15GB_price": integer,
        "MTN_20GB_price": integer,
        "Glo_500MB_price": integer,
        "Glo_1GB_price": integer,
        "Glo_2GB_price": integer,
        "Glo_3GB_price": integer,
        "Glo_5GB_price": integer,
        "Glo_7GB_price": integer,
        "Glo_10GB_price": integer,
        "Glo_12GB_price": integer,
        "Glo_16pt_5GB_price": integer,
        "Glo_25GB_price": integer,
        "Glo_42GB_price": integer,
        "Glo_78GB_price": integer,
        "Glo_100GB_price": integer,
        "Glo_115GB_price": integer,
        "Airtel_500MB_price": integer,
        "Airtel_1GB_price": integer,
        "Airtel_1pt_5GB_price": integer,
        "Airtel_2GB_price": integer,
        "Airtel_3GB_price": integer,
        "Airtel_5GB_price": integer,
        "Airtel_4pt_5GB_price": integer,
        "Airtel_6GB_price": integer,
        "Airtel_10GB_price": integer,
        "Airtel_11GB_price": integer,
        "Airtel_20GB_price": integer,
        "Airtel_40GB_price": integer,
        "Airtel_110GB_price": integer,
        "_9Mobile_500MB_price": integer,
        "_9Mobile_1GB_price": integer,
        "_9Mobile_1pt_5GB_price": integer,
        "_9Mobile_2GB_price": integer,
        "_9Mobile_3GB_price": integer,
        "_9Mobile_4pt_5GB_price": integer,
        "_9Mobile_5GB_price": integer,
        "_9Mobile_10GB_price": integer,
        "_9Mobile_11GB_price": integer,
        "_9Mobile_15GB_price": integer,
        "_9Mobile_20GB_price": integer,
        "_9Mobile_40GB_price": integer
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
    
### GOTV

    {
        "cableplan_id": "34",
        "cablename_id": "GOTV",
        "package": "GOtv Smallie - Monthly",
    },
    {
        "cableplan_id": "16",
        "cablename_id": "GOTV",
        "package": "GOtv Jinja",
    },
    {
        "cableplan_id": "18",
        "cablename_id": "GOTV",
        "package": "GOtv Smallie",
    },
    {
        "cableplan_id": "35",
        "cablename_id": "GOTV",
        "package": "GOtv Smallie - Quarterly",
    },
    {
        "cableplan_id": "17",
        "cablename_id": "GOTV",
        "package": "GOtv Jolli",
    },
    {
        "cableplan_id": "2",
        "cablename_id": "GOTV",
        "package": "GOtv Max",
    },
    {
        "cableplan_id": "47",
        "cablename_id": "GOTV",
        "package": "Gotv-supa-6400-monthly",
    },
    {
        "cableplan_id": "36",
        "cablename_id": "GOTV",
        "package": "GOtv Smallie - Yearly",
    }

### DSTV
    {
        "cableplan_id": "21",
        "cablename_id": "DSTV",
        "package": "DStv Great Wall Standalone",
    },
    {
        "cableplan_id": "20",
        "cablename_id": "DSTV",
        "package": "DStv Padi",
    },
    {
        "cableplan_id": "33",
        "cablename_id": "DSTV",
        "package": "ExtraView Access",
    },
    {
        "cableplan_id": "32",
        "cablename_id": "DSTV",
        "package": "DStv HDPVR Access Service",
    },
    {
        "cableplan_id": "6",
        "cablename_id": "DSTV",
        "package": "DStv Yanga",
    },
    {
        "cableplan_id": "27",
        "cablename_id": "DSTV",
        "package": "DStv Yanga + ExtraView",
    },
    {
        "cableplan_id": "28",
        "cablename_id": "DSTV",
        "package": "DStv Padi + ExtraView",
    },
    {
        "cableplan_id": "19",
        "cablename_id": "DSTV",
        "package": "DStv Confam",
    },
    {
        "cableplan_id": "23",
        "cablename_id": "DSTV",
        "package": "DStv Asia",
    },
    {
        "cableplan_id": "26",
        "cablename_id": "DSTV",
        "package": "DStv Confam + ExtraView",
    },
    {
        "cableplan_id": "29",
        "cablename_id": "DSTV",
        "package": "DStv Compact + Extra View",
    },
    {
        "cableplan_id": "7",
        "cablename_id": "DSTV",
        "package": "DStv Compact",
    },
    {
        "cableplan_id": "8",
        "cablename_id": "DSTV",
        "package": "DStv Compact Plus",
    },
    {
        "cableplan_id": "31",
        "cablename_id": "DSTV",
        "package": "DStv Compact Plus - Extra View",
    },
    {
        "cableplan_id": "5",
        "cablename_id": "DSTV",
        "package": "Asian Bouqet",
    },
    {
        "cableplan_id": "25",
        "cablename_id": "DSTV",
        "package": "DStv Premium Asia",
    },
    {
        "cableplan_id": "30",
        "cablename_id": "DSTV",
        "package": "DStv Premium + Extra View",
    },
    {
        "cableplan_id": "9",
        "cablename_id": "DSTV",
        "package": "DStv Premium",
    },
    {
        "cableplan_id": "24",
        "cablename_id": "DSTV",
        "package": "DStv Premium French",
    }
### STARTIMES
    {
        "cableplan_id": "42",
        "cablename_id": "STARTIME",
        "package": "Nova - 1 Day",
    },
    {
        "cableplan_id": "43",
        "cablename_id": "STARTIME",
        "package": "Basic - 160 Naira - 1 Day",
    },
    {
        "cableplan_id": "44",
        "cablename_id": "STARTIME",
        "package": "Smart - 1 Day",
    },
    {
        "cableplan_id": "37",
        "cablename_id": "STARTIME",
        "package": "Nova - 1 Week",
    },
    {
        "cableplan_id": "45",
        "cablename_id": "STARTIME",
        "package": "Classic - 1 Day",
    },
    {
        "cableplan_id": "46",
        "cablename_id": "STARTIME",
        "package": "Super - 1 Day",
    },
    {
        "cableplan_id": "38",
        "cablename_id": "STARTIME",
        "package": "Basic - 1 Week",
    },
    {
        "cableplan_id": "39",
        "cablename_id": "STARTIME",
        "package": "Smart - 1 Week",
    },
    {
        "cableplan_id": "14",
        "cablename_id": "STARTIME",
        "package": "Nova - 1 Month",
    },
    {
        "cableplan_id": "40",
        "cablename_id": "STARTIME",
        "package": "Classic 1 Week",
    },
    {
        "cableplan_id": "41",
        "cablename_id": "STARTIME",
        "package": "Super - 1 Week",
    },
    {
        "cableplan_id": "12",
        "cablename_id": "STARTIME",
        "package": "Basic - 1 Month",
    },
    {
        "cableplan_id": "13",
        "cablename_id": "STARTIME",
        "package": "Smart - 1 Month",
    },
    {
        "cableplan_id": "11",
        "cablename_id": "STARTIME",
        "package": "Classic - 1 Mont",
    },
    {
        "cableplan_id": "15",
        "cablename_id": "STARTIME",
        "package": "Super - 1 Month",
    }

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
        "id": 1,
        "GOtv_Smallie_Monthly_price": Integer,
        "GOtv_Jinja_price": Integer,
        "GOtv_Smallie_price": Integer,
        "GOtv_Smallie_Quarterly_price": Integer,
        "GOtv_Jolli_price": Integer,
        "GOtv_Max_price": Integer,
        "Gotv_supa_monthly_price": Integer,
        "GOtv_Smallie_Yearly_price": Integer,
        "DStv_Great_Wall_Standalone_price": Integer,
        "DStv_Padi_price": Integer,
        "ExtraView_Access_price": Integer,
        "DStv_HDPVR_Access_Service_price": Integer,
        "DStv_Yanga_price": Integer,
        "DStv_Yanga_ExtraView_price": Integer,
        "DStv_Padi_plus_ExtraView_price": Integer,
        "DStv_Confam_price": Integer,
        "DStv_Asia_price": Integer,
        "DStv_Confam_plus_ExtraView_price": Integer,
        "DStv_Compact_plus_Extra_View_price": Integer,
        "DStv_Compact_price": Integer,
        "DStv_Compact_Plus_price": Integer,
        "DStv_Compact_Plus_Extra_View_price2": Integer,
        "DStv_Asia_Bouqet_price": Integer,
        "DStv_Premium_Asia_price": Integer,
        "DStv_Premium_plus_Extra_View_price": Integer,
        "DStv_Premium_price": Integer,
        "DStv_Premium_French_price": Integer,
        "Nova_1_Day_price": Integer,
        "Basic_1_Day_price": Integer,
        "Smart_1_Day_price": Integer,
        "Nova_1_Week_price": Integer,
        "Classic_1_Day_price": Integer,
        "Super_1_Day_price": Integer,
        "Basic_1_Week_price": Integer,
        "Smart_1_Week_price": Integer,
        "Nova_1_Month_price": Integer,
        "Classic_1_Week_price": Integer,
        "Super_1_Week_price": Integer,
        "Basic_1_Month_price": Integer,
        "Smart_1_Month_price": Integer,
        "Classic_1_Month_price": Integer,
        "Super_1_Month_price": Integer
    }



    

# API Documentation
## Base URL

[https://minuza.brd.rw](https://minuza.brd.rw)

## Endpoint

`/api/recovery/ippis/check`

## HTTP Method

POST

## Request Body

The request requires a JSON object in the body with the following format:
``` json

{
    "nationalId": {{national_id_number}}
}
```

where {{national_id_number}} is the national ID number of the beneficiary to be searched and is composed of the 13 first digits of the national ID number.

## Headers

The API requires basic authentication. Pass the authentication token in the header as Authorization. The username and password will be provided separately by the API provider (Minuza).


## Example Request

``` bash
Authorization: Basic jDJKSFDUNKGFDt6434n=
```

## Response Body

The response is a JSON object with the following format:

``` json

{
    "status": 200,
    "message": "Minuza Beneficiary Status",
    "data": {
        "postName": "Jean Luc",
        "surName": "Karangwa",
        "nationalIdSearched": "1199696306486",
        "nationalId": "1199696306486678",
        "currency": "RWF",
        "totalLoanAmount": 6355954,
        "remainingLoanAmount": 4790896,
        "totalPaid": 1565058
    }
}
```
## Response Fields

| Field | Description |
| --- | --- |
| status | HTTP status code |
| message | Message describing the response |
| data | Data returned by the API |
| postName | Name of the post |
| surName | Surname of the beneficiary |
| nationalIdSearched | National ID number of the beneficiary searched |
| nationalId | National ID number of the beneficiary |
| currency | Currency of the loan |
| totalLoanAmount | Total loan amount |
| remainingLoanAmount | Remaining loan amount |
| totalPaid | Total amount paid |

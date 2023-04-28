# API Documentation

## Base URL

[https://educapi.brd.rw](https://educapi.brd.rw)

## Endpoint

`/api/auth/login`

## HTTP Method

POST

## Request Body
```json
{
  "username": "string",
  "password": "string"
}
```


This endpoint will allow allow you to receive an autentication tocken for each of your request if the usename and passowrd provided are correct

## Response body
```json
{
  "status": 200,
  "message": "Successfully loggedIn",
  "data": {
    "user": {
      "id": 5,
      "firstName": "xxxxxx",
      "lastName": "xxxxx",
      "username": "xxxxxxxxx",
      "roleId": 5,
      "isActive": true,
      "loggedInAt": "2023-04-24T12:20:30.316Z",
      "createdAt": "2023-04-24T10:04:21.289Z",
      "updatedAt": "2023-04-24T12:20:30.317Z"
    },
    "token": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  }
}
```
---------------------------------------------------------------------------------------------------------------------------------------------

`/api/payments/ipps`

## HTTP Method

POST

## Request Body

The request requires a JSON object in the body with the following format:

```json

{
    "nationalId": {{national_id_number}}
}
```

where {{national_id_number}} is the national ID number of the beneficiary to be searched and is composed of the 13 first digits of the national ID number.

## Headers

The API now requires JWT authentication. Pass the JWT token received on login in the header as Authorization. The token will be provided separately by the API provider (Minuza). 

## Example Request

```bash
Authorization: Barea xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## Response Body

The response is a JSON object with the following format:

```json
{
	"status": 200,
	"message": "Minuza Beneficiary Status",
	"data": {
		"postName": "xxx xxx",
		"surName": "xxxx",
		"nationalIdSearched": "xxxxxxxx",
		"nationalId": "xxxxxxxx",
		"currency": "RWF",
		"totalLoanAmount": xxxxxx,
		"remainingLoanAmount": xxxxxxx,
		"totalPaid": xxxxxxx
	}
}
```

## Response Fields

| Field               | Description                                    |
| ------------------- | ---------------------------------------------- |
| status              | HTTP status code                               |
| message             | Message describing the response                |
| data                | Data returned by the API                       |
| postName            | Name of the post                               |
| surName             | Surname of the beneficiary                     |
| nationalIdSearched  | National ID number of the beneficiary searched |
| nationalId          | National ID number of the beneficiary          |
| currency            | Currency of the loan                           |
| totalLoanAmount     | Total loan amount                              |
| remainingLoanAmount | Remaining loan amount                          |
| totalPaid           | Total amount paid                              |

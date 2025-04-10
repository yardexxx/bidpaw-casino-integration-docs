---
sidebar_position: 2
---

# Money withdrawal request

A request to withdraw money from the user is executed when the player:

- initiates the purchase of bids
- initiates payment for the won auction

![Bids Purchase scheme](/img/bids-purch-scheme.jpeg)


#### Request header (HTTP Header)

| Parameter Name | Description       | Optional / Mandatory | Data type |
|----------------|-------------------|----------------------|-----------|
| sign           | Request signature | Mandatory            |  string   |

#### Request parameters
| Parameter Name | Description                         | Optional / Mandatory | Data type |
|----------------|-------------------------------------|----------------------|-----------|
| method         | charge / credit                     | Mandatory            | string    |
| userId         | User identifier from your system    | Mandatory            | string    |
| clientId       | Casino id                           | Mandatory            | string    |
| sessionId      | Session identifier                  | Mandatory            | string    |
| amount         | Amount to withdraw/deposit in Cents | Mandatory            | integer   |
| currency       | ISO currency code                   | Mandatory            | string    |
| transactionId  | Transaction ID                      | Mandatory	           | string    |

#### Response parameters

A response to request is expected to be made in JSON format. Response Parameters:

| Parameter Name    | Description                                                                            | Optional / Mandatory | Data type |
|-------------------|----------------------------------------------------------------------------------------|----------------------|-----------|
| errorCode         | Error code if the request does not come through successfully, and 0 in any other case. | Mandatory            | integer   |
| errorDescription  | Error description in case the request has not been successfully processed.             | Optional             | string    |

##### Response example
```json
{
    "errorCode": 0,
    "errorDescription":""
}
```

```json
{
    "errorCode": 1,
    "errorDescription":"Not Enough Balance"
}
```
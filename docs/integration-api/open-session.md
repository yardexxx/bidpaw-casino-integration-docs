---
sidebar_position: 4
---

# Open Session

In order to open session, use the link sent as a response for the request to open an iframe. The following diagram describes the interactions between a player, your casino and BidPaw when a user opens the lobby for the first time after the registration.

![Authorization scheme](/img/auth-scheme.jpeg)

The link to open the lobby (iframeURL) may be opened any way that suits you: in a new window, in the current window, in an iframe.

#### Creating a session

#### Request URL

GET `http(s)://API_URL/api/casino/open-session/?clientId={CLIENT_ID}&nick={optional_username}&userId={USER_ID_FROM_YOUR_SYSTEM}`

#### Request header (HTTP Header)

| Parameter Name | Description       | Optional / Mandatory |
|----------------|-------------------|----------------------|
| sign           | Request signature | Mandatory            |

#### Request parameters

| Parameter Name | Description                                          | Optional / Mandatory |
|----------------|------------------------------------------------------|----------------------|
| clientId       | Casino  identifier that is sent in the request line. | Mandatory            |
| userId         | User identifier.	                                    | Mandatory            |
| nick           | nickName or displayName (variable) may be sent.      | Optional             |


#### Response parameters


| Parameter Name | Description   | Optional / Mandatory |
|----------------|---------------|----------------------|
| iframeURL      | URL to open   | Mandatory            |

#### Errors returned

| HTTP Code | Message           | Description                                      |
|-----------|-------------------|--------------------------------------------------|
| 400       | Not valid request | Incorrect request signature or client id missing |
| 500       | -                 | Server Error                                     |


#### Example of response

```json
{
  "iframeURL": "https://bidpaw-tap-to-earn.web.app/auctions?token=...&session=...&casinoId=..."
}
```

#### Example of error response

```json
{
  "data": null,
  "status": 400,
  "message": "Not valid request"
}
```
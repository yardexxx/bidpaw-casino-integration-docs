---
sidebar_position: 2
---

# Interaction protocol

Communication via HTTP(S)-queries in JSON API format is used for integration. 
The query parameters can be passed in the query string (GET method) and in the query body (POST method). The response is passed in the JSON API format.

It is necessary to set __'content-type'__ to __'application/json; charset=UTF-8'__ in your request header.\
Also note that every request made should include __sign__ header.

### API query template

``http(s)://API_URL/{methodName}?[parameterName=parameterValue]&clientId={your casino ID}``

The following __headers__ are required for every query:

| Parameter Name | Data Type | Description      |
|----------------|-----------|------------------|
| sign           | String    | Query signature  |


The following __parameters__ are required for auth query:

| Parameter Name | Data Type | Description     |
|----------------|-----------|-----------------|
| clientId       | Varchar   | Your casino ID  |
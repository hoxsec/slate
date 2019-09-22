# Error Codes

Flightdata.nl API uses the following error codes: <br/>
If you get an error that is not listed here please contact
us at support@flightdata.nl

Error Code | Description
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong or invalid.
403 | Forbidden -- Cannot call with your API key.
404 | Not Found -- Cannot find API call route.
405 | Method Not Allowed -- Cannot call with invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The requested route has been removed from our servers.
418 | Flightdata API Reserved.
429 | Too Many Requests -- Too many requests with API key.
500 | Internal Server Error -- API Problem, if statuspage is saying otherwise please contact support@flightdata.nl.
503 | Service Unavailable -- API Service is offline for maintance or upgrade.

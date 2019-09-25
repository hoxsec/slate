---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - php
  - javascript

toc_footers:
  - <p>v1.0</p>
  - <a href='#'>&copy; Flightdata.nl 2019</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the documentation of the flightdata.nl API. 

This document will always be kept up to date with any changes or updates.

The use of this api requires an API_KEY which you can obtain by creating an account on [Flightdata.nl](https://flightdata.nl)

# Authentication

Before using our API you need to have an account with a valid API_KEY. (found at your dashboard)

If you do not have an API_KEY and/or account you can register here:  [flightdata.nl/register](https://flightdata.nl/register).

<aside class="warning">
You must replace <code>{API_KEY}</code> with your own personal API key.
</aside>

# API - Airports

## Get All Airports (World)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airports \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airports",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airports");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "00AK": {
        "icao": "00AK",
        "iata": "",
        "name": "Lowell Field",
        "city": "Anchor Point",
        "state": "Alaska",
        "country": "US",
        "elevation": 450,
        "lat": 59.94919968,
        "lon": -151.695999146,
        "tz": "America/Anchorage"
    },
    .....
}
```

Retrieve every airport in the world.
List also includes old and military airports.

### HTTP Request

`GET https://api.flightdata.nl/v1/airports`

<!-- ### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
continent | true | 
available | true | If set to false, the result will include kittens that have already been adopted. -->


## Get Airports Continent

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airports/continent/{CONTINENT} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airports/continent/{CONTINENT}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airports/continent/{CONTINENT}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airports": [
        {
            "icao": "BKPR",
            "iata": "PRN",
            "name": "Pristina International Airport",
            "city": "Prishtina",
            "state": "Pristina",
            "country": "KS",
            "elevation": 1789,
            "lat": 42.5727996826,
            "lon": 21.0358009338,
            "tz": "Europe/Belgrade"
        },
        .....
```

Retrieve every airport in the given continent.

### HTTP Request

`GET https://api.flightdata.nl/v1/airports/continent/{continent}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
continent | true    | Europe, America


## Get Airports Country

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airports/country/{country} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airports/country/{country}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airports/country/{COUNTRY}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airports": [
        {
            "icao": "EHAL",
            "iata": "",
            "name": "Ameland Airport",
            "city": "Ameland",
            "state": "Friesland",
            "country": "NL",
            "elevation": 11,
            "lat": 53.4516983032,
            "lon": 5.6772198677,
            "tz": "Europe/Amsterdam"
        },
        .....
```

Retrieve every airport in the given country.

### HTTP Request

`GET https://api.flightdata.nl/v1/airports/country/{country}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
country | true    | NL, DE, FR (Alpha-2)

## Get Airports (ICAO & IATA)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airport/{airport} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airport/{airport}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airport/{airport}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airport": {
        "icao": "EHAM",
        "iata": "AMS",
        "name": "Amsterdam Airport Schiphol",
        "city": "Amsterdam",
        "state": "North-Holland",
        "country": "NL",
        "elevation": -11,
        "lat": 52.3086013794,
        "lon": 4.7638897896,
        "tz": "Europe/Amsterdam"
    }
}
```

Get airport by ICAO or IATA code at the same time.

### HTTP Request

`GET https://api.flightdata.nl/v1/airport/{airport}`

### Query Parameters

Parameter | Required | Example
--------- | -------  |  -------
airport | true       | EHAM (ICAO) or AMS (IATA)


## Get Airport (ICAO)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airport/icao/{airport} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airport/icao/{airport}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airport/icao/{airport}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airport": {
        "icao": "EHAM",
        "iata": "AMS",
        "name": "Amsterdam Airport Schiphol",
        "city": "Amsterdam",
        "state": "North-Holland",
        "country": "NL",
        "elevation": -11,
        "lat": 52.3086013794,
        "lon": 4.7638897896,
        "tz": "Europe/Amsterdam"
    }
}
```

Search airport by ICAO code. 

If you wish to search by ICAO and IATA code at the same time, look at our other API.

### HTTP Request

`GET https://api.flightdata.nl/v1/airport/icao/{airport}`

### Query Parameters

Parameter | Required | Example
--------- | -------  | -------
airport   | true     | EHAM


## Get Airport (IATA)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airport/iata/{airport} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airport/iata/{airport}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airport/iata/{airport}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airport": {
        "icao": "EHAM",
        "iata": "AMS",
        "name": "Amsterdam Airport Schiphol",
        "city": "Amsterdam",
        "state": "North-Holland",
        "country": "NL",
        "elevation": -11,
        "lat": 52.3086013794,
        "lon": 4.7638897896,
        "tz": "Europe/Amsterdam"
    }
}
```

Search airport by IATA code. 

If you wish to search by ICAO and IATA code at the same time, look at our other API.

### HTTP Request

`GET https://api.flightdata.nl/v1/airport/iata/{airport}`

### Query Parameters

Parameter | Required | Example
--------- | -------  | -------
airport   | true     | AMS


# API - Airlines

## Get All Airlines (World)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airlines \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airlines",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airlines");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
[
    {
        "id": 3090,
        "name": "KLM Royal Dutch Airlines",
        "alias": "",
        "iata": "KL",
        "icao": "KLM",
        "callsign": "KLM",
        "country": "Netherlands",
        "active": "Y"
    },
    .....
]
```

Retrieve every airline in the world.

### HTTP Request

`GET https://api.flightdata.nl/v1/airlines`



## Get Airlines Country

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airlines/country/{country} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airlines/country/{country}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airlines/country/{COUNTRY}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airlines": [
        {
            "id": 1299,
            "name": "Arkefly",
            "alias": "",
            "iata": "OR",
            "icao": "TFL",
            "callsign": "ARKEFLY",
            "country": "Netherlands",
            "active": "Y"
        },
        .....
```

Retrieve every airline in the given country.

### HTTP Request

`GET https://api.flightdata.nl/v1/airlines/country/{country}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
country | true    | Netherlands, France


## Get Active Airlines Country

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airlines/country/{country}/active/{active} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airlines/country/{country}/active/{active}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airlines/country/{country}/active/{active}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airlines": [
        {
            "id": 575,
            "name": "Air Exel",
            "alias": "",
            "iata": "XT",
            "icao": "AXL",
            "callsign": "EXEL COMMUTER",
            "country": "Netherlands",
            "active": "Y"
        },
        .....
```

Retrieve every active or non-active airline in the given country.

### HTTP Request

`GET https://api.flightdata.nl/v1/airlines/country/{country}/active/{active}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
country | true    | Netherlands, France
active  | true    | yes, no


## Get Active Airlines (World)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airlines/active/{active} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airlines/active/{active}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airlines/active/{active}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airlines": [
        {
            "id": 2,
            "name": "135 Airways",
            "alias": "",
            "iata": "",
            "icao": "GNL",
            "callsign": "GENERAL",
            "country": "United States",
            "active": "N"
        },
        .....
```

Retrieve every active or non-active airline in the world.

### HTTP Request

`GET https://api.flightdata.nl/v1/airlines/active/{active}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
active  | true    | yes, no





## Get Airline (ICAO & IATA)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airline/{airline} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airline/{airline}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airline/{airline}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airline": {
        "id": 3320,
        "name": "Lufthansa",
        "alias": "",
        "iata": "LH",
        "icao": "DLH",
        "callsign": "LUFTHANSA",
        "country": "Germany",
        "active": "Y"
    }
}
```

Get airline by ICAO or IATA code at the same time.

### HTTP Request

`GET https://api.flightdata.nl/v1/airline/{airline}`

### Query Parameters

Parameter | Required | Example
--------- | ------- |  -------
airline  | true    | LH (IATA) or DLH (ICAO)










## Get Airline (ICAO)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airline/icao/{airline} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airline/icao/{airline}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airline/icao/{airline}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airline": {
        "id": 3090,
        "name": "KLM Royal Dutch Airlines",
        "alias": "",
        "iata": "KL",
        "icao": "KLM",
        "callsign": "KLM",
        "country": "Netherlands",
        "active": "Y"
    }
}
```

Get airline by ICAO code. 

If you wish to search by ICAO and IATA code at the same time, look at our other API.

### HTTP Request

`GET https://api.flightdata.nl/v1/airline/icao/{airline}`

### Query Parameters

Parameter | Required | Example
--------- | -------  | -------
airline   | true     | KLM







## Get Airline (IATA)

```shell
curl -X GET \
  https://api.flightdata.nl/v1/airline/iata/{airline} \
  -H 'Authorization: Bearer {API_KEY}' \
```

```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.flightdata.nl/v1/airline/iata/{airline}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => array(
    "Authorization: Bearer {API_KEY}",
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

```javascript
var data = null;

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function () {
  if (this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("GET", "https://api.flightdata.nl/v1/airline/iata/{airline}");
xhr.setRequestHeader("Authorization", "Bearer {API_KEY}");

xhr.send(data);
```

> Response:

```json
{
    "airline": {
        "id": 333,
        "name": "Air Baltic",
        "alias": "",
        "iata": "BT",
        "icao": "BTI",
        "callsign": "AIRBALTIC",
        "country": "Latvia",
        "active": "Y"
    }
}
```

Get airline by IATA code. 

If you wish to search by ICAO and IATA code at the same time, look at our other API.

### HTTP Request

`GET https://api.flightdata.nl/v1/airline/iata/{airline}`

### Query Parameters

Parameter | Required | Example
--------- | -------  | -------
airline   | true     | BT
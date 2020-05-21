# API Authentication

## Example URI

``` 
/api/v1/invoice/create
```

## Query Params

| Key | Type | Description |
| --- | --- | --- |
| ts | int | Unix Timestamp (in seconds) |
| nonce | string | Random String (Unique in at least 30 minutes) |

## Headers

| Header | Description |
| --- | --- | --- |
| X-Access-Key | Your Access Key |
| X-Signature | Request Signature (See [How to make a signature](#how-to-make-a-signature) ) |

# How to make a signature

Signatures are calculated using HMAC SHA3-384.<br>
Use the full URI (e.g. /api/v1/invoice/create?ts=1234567890&nonce=abcd12345) as data, your Secret Key as key.<br>
The hash calculation results should be expressed as a hexadecimal string, which is the signature and case insensitive.

## PHP Example

Requires PHP 7.1.0 or later.

``` 
<?php

$secret_key = 'r9WzuQReIELAkDhG6gBjpyldUmxV2sHP3Yt8FONqCbfnTX7cS05ZoMiK1awJv4';

$uri = '/api/v1/invoice/create?ts=' . time() . '&nonce=' . md5(random_bytes(16));

/** @var string $sign the signature */
$sign = hash_hmac('SHA3-384', $uri, $secret_key);  // maker
```

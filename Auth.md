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
| --- | --- |
| X-Access-Key | Your Access Key |
| X-Signature | Request Signature ([How to make a signature?](/Signature.md) ) |


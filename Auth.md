# API Authentication

## Query Params

| Key | Type | Description |
| --- | --- | --- |
| ts | int | Unix Timestamp (in seconds) |
| nonce | string | Random String (Unique in at least 30 minutes) |

## Headers

| Header | Description |
| --- | --- |
| X-Access-Key | Your Access Key |
| X-Signature | Request Signature (See [Signature](#signature) part) |

## Signature

Use URI as input data (e.g. `/v1/invoice/create?ts=1234567890&nonce=abcd12345`)<br>
For more details check out [How to make a signature?](/Signature.md).

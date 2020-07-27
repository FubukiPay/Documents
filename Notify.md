# Notify

This notification will be triggered when the customer's payment is confirmed.<br>
Also, the funds have been credited to your merchant wallet.

## URL

Set by the merchant when creating the order.

## Method

POST

## Headers

| Header | Description |
| --- | --- |
| Content-Type | application/x-www-form-urlencoded |
| X-Notify-Key | The notify key we returned with invoice creation |
| X-Access-Key | The Access Key that creates this invoice (Only available if created from API) |
| X-Signature | Signature of notify URL (See [How to make a signature?](/Signature.md)) (Only available if created from API) |

## Body

| Key | Type | Description |
| --- | --- | --- |
| serial | int | -- |
| title | string | Invoice Title |
| base_currency | string | USD / CNY |
| amount | float | -- |
| merchant_tradeno | string | Merchant's internal order identifier |
| pay_time | int | Unix Timestamp |
| currency | string | Currency name that user actually paid with, human readable |
| rate | float | Exchange rate from base currency |
| pay_amount | float | Customer actual paid amount |
| fees | float | Fees we charge |
| fees_payer | int | Who paid the fee, 1/Merchant, 2/Customer |
| wallet | string | Merchant wallet where this funds went |

## Response

Required response with 2xx status code within 10 seconds or it will be treated as a failure.

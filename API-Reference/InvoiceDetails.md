# Invoice Details

## URL

``` 
GET https://api.fubuki.us/v1/invoice/{identity}
```

## Authentication

See [Auth](Auth.md)

## Path Parameters

| Name | Required | Description |
| --- | --- | --- | --- |
| identity | Yes | Invoice Serial / Invoice Token / Merchant Trade No. |

## Example Response

``` 
{
    "code": 0,
    "msg": "",
    "data": {
        "serial": "20200612142275806374114514",
        "token": "U3sCqKzvKsEvuL3E9QUDsmeDSg4JiQk4JX2ayXtCVAeNuK4bz4UDTAQ2Ng5LbWpBt",
        "title": "Fubuki Pay Demo Company Order",
        "base_currency": "USD",
        "amount": 10,
        "merchant_tradeno": "6d4fb35bafa46f2a9ac9f123ba9320cd",
        "notify_url": null,
        "return_url": null,
        "notify_key": "g3feYCcvVCxZcNra4XdfBsjxtfLSNTVv",
        "paid": false,
        "pay_time": 0,
        "fees_payer": 1,
        "notified": false,
        "create_time": 1591944172,
        "status": "pending",
        "status_text": "Pending",
        "pay_currency_code": null,
        "pay_currency": null,
        "wallet": null,
        "rate": null,
        "pay_amount": null,
        "fees": null,
        "notify_http_code": null,
        "notify_time": null
    }
}
```

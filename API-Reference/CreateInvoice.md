# Create Invoice

## URL

``` 
POST https://api.fubuki.us/v1/invoice/create?ts=1591128413&nonce=zcV8h5QRuK2EM
```

## Authentication

See [Auth](Auth.md)

## Body

> We recommend including order secret key in the `notify_url` .

| Key | Required | Type | Description |
| --- | --- | --- | --- |
| base_currency | Yes | string | USD / CNY |
| amount | Yes | float | Order amount in `base_currency` |
| fees_payer | Yes | int | Who will pay the fees for this invoice. <code>1</code> for the merchant, <code>2</code> for the customer. |
| merchant_tradeno | No | string | Merchant's internal order identifier, it should within 32 ASCII characters.<br>We will generate one if not provided. |
| title | No | string | Invoice title |
| notify_url | No | string | An HTTP URL that we will notify when the customer has paid. |
| return_url | No | string | An HTTP URL that customers will redirect to when they paid or canceled. |

## Example Response

``` 
{
    "code": 0,
    "msg": "",
    "data": {
        "payment_url": "https://pay.fubuki.us/invoice/X1lSLnTHlYzj2SUfhjzmS5Ee3gIVob7xSmEnVwH0VdJHm4RunZLfgJ8Rfa8BShzs",
        "serial": "20200525232272518997357424",
        "token": "X1lSLnTHlYzj2SUfhjzmS5Ee3gIVob7xSmEnVwH0VdJHm4RunZLfgJ8Rfa8BShzs",
        "title": "Example Company Limited Order",
        "merchant_tradeno": "0d6e7633dd926ea44f8b24fd0034e518",
        "base_currency": "USD",
        "amount": 233,
        "notify_url": "http://example.com/1919810",
        "return_url": "http://example.com/114514",
        "notify_key": "tEezbu97WqihzoMXj30K8wCGstoWYUn5",
        "fees_payer": 2,
        "create_time": 1590420489
    }
}
```

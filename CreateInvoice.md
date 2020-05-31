# Create Invoice

## URL

``` 
POST https://api.fubuki.us/v1/invoice/create
```

## Authentication

See [Auth](/Auth.md)

## Body

> We recommend including the internal order number or identifier in the `notify_url` .

| Key | Required | Type | Description |
| --- | --- | --- | --- |
| title | No | string | Invoice title |
| base_currency | Yes | string | USD / CNY |
| amount | Yes | float | Order amount in `base_currency` |
| merchant_tradeno | No | string | Merchant's internal order identifier, it should within 32 ASCII characters.<br>We will generate one if not provided. |
| notify_url | Yes | string | An HTTP URL that we will notify when the customer has paid. |
| return_url | Yes | string | An HTTP URL that customers will redirect to when they paid or canceled. |
| fees_payer | Yes | int | Who will pay the fees for this invoice. <code>1</code> for the merchant, <code>2</code> for the customer. |

## Response

``` 
{
    "ret": 0,
    "msg": "",
    "data": {
        "payment_url": "http://localhost:8000/invoice/X1lSLnTHlYzj2SUfhjzmS5Ee3gIVob7xSmEnVwH0VdJHm4RunZLfgJ8Rfa8BShzs",
        "serial": "20200525232272518997357424",
        "token": "X1lSLnTHlYzj2SUfhjzmS5Ee3gIVob7xSmEnVwH0VdJHm4RunZLfgJ8Rfa8BShzs",
        "title": "WooMai Network Order",
        "merchant_tradeno": "114514asdfgh",
        "base_currency": "USD",
        "amount": 233,
        "notify_url": "http://example.com/1919810",
        "return_url": "http://example.com/114514",
        "fees_payer": 2,
        "create_time": 1590420489
    }
}
```

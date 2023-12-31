## Package for an [ITPay](https://itpay.app) API

## About
Just a small but powerful package-wrapper for an [ITPay](https://itpay.app) API

## Usage
`ITPaySDK` can help you to create and retrieve payment info, get information about your account's balance and toggle bill activity

## Documentation
Official docs can be found here on the [APIs webpage](https://itpay.app/merchant/api/)

## Installation
`pip install itpaysdk`

## Requirements
- Python 3.11
- aiohttp

## Features
- Asynchronous
- LightWeight

## Basic example
```
from ITPaySDK import ITPayAPI, Currency, PaymentType


client = ITPayAPI(
    shop_id=YOUR_SHOP_ID, 
    token=YOUR_TOKEN,
)

#  Get balance
await client.balance()

#  Create bill
response = await client.create_bill(
    amount=100.05,
    order_id=123123,
    description="Lorem ipsum dollar",
    type=PaymentType.one_time,
    currency_in=Currency.RUB,
    payer_pays_commission=True
) 

#  Check bill status and related info
response = await client.bill_status(
    bill_id=123123
)

#  Deactivate the bill
response = await client.toggle_activity(
    bill_id=123123,
    active=False
)
```

## GitHub

[Repo](https://github.com/JMURv/ITPaySDK/tree/main) of the project
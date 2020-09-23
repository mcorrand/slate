# Webhooks
 
## Universal Webhook

Our recommended webhook fires on any change to a reservation you own (including related resource changes such as customer, invoice and payments).

The payload you receive contains:

```json
[
{
    "signature":
    {
        "id": 1,
        "min_age": 0,
        "max_age": 2,
        "verbose": "from age 0 (inclusive) to 2"
    },
    "listings": [
    {
        "id": 3,
        "price_dollars": null,
        "price_percent": "-100.00",
        "package": null,
        "verbose": "100.00% off"
    },
    // more listings
    ]
},
// more discounts
]
```

*   An object named ‘signature’ you will be able to use to verify the request is coming from us
*   The Id of the reservation that changed, so you can send a query to the Reservation Status endpoint and get the latest info.

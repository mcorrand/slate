## Age Discounts List

### HTTP Request

`GET /partners/agediscounts/`

### Query Parameters

None

### Response Body

> The json response looks like this:

```json
[
{
    "policy":
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
    # more listings
    ]
},
# more discounts
]
```

Age Discounts objects comprise a `policy` object which determines whether a guest is eligible to a discount, and one or more `listing` objects which determine the amount of the discount, based on the package the guest is booking.

Object | Key | Type | Description
--------- | ------- | ------- | -----------
**policy** |
| | id | Integer | The policy's id
| | min_age | Integer | Minimum age at arrival to be eligible for the discount, **inclusive**
| | max_age | Integer | Maximum age at arrival to be eligible for the discount, **exclusive**
| | verbose | String | A verbose representation of the policy terms
**listings**|  |
| | id | Integer | The listing's id
| | price_dollars | Integer or null | The negative amount, in dollars, of the discount; will be null if the discount is percentage based
| | price_percent | Integer or null | The negative percentage, in dollars, of the discount; will be null if the discount is dollar based
| | package | Integer or null | If null, this is the default listing; otherwise, this is the id of the package the listing applies to. Package specific listings supercede the default. 
| | verbose | String | A verbose representation of the listing



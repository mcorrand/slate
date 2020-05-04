## Inquiry Creation

### HTTP Request

`POST /partners/inquiry/`

### Request Body

> The json request looks like this:

```json
{
    "inquired_for_adults": 2,
    "inquired_for_kids": 0,
    "arrival_date": "2020-05-04",
    "departure_date": "2020-05-06",
    "customer":
    {
        "name": "Customer Name",
        "email": "customeremail@example.com",
        "phone": "(123)456-7890",
        "address_line1": "Address line 1",
        "address_line2": "Address line 2",
        "city": "City",
        "zip": "12345",
        "state": "Wyoming",
        "country": "United States"
    }
}
```

Key | Type | Required | Description
--------- | ------- | ------- | -----------
inquired_for_adults | Integer | Yes | Number of adults in party
inquired_for_kids | Integer | Yes | Number of kids in party - usual quoting process then requests the birth dates; we may have to move that in this endpoint
arrival_date | String | Yes | 'YYYY-MM-DD' formatted arrival date, must be in season. 
departure_date | String | Yes | 'YYYY-MM-DD' formatted departure date.
**customer** |
name | String | Yes | The customer's name (required)
email | String | Yes | The customer's email address (required
phone | String | Yes | The customer's phone number
address_line1 | String | No | The customer's address line #1
address_line2 | String | No | The customer's address line #1
city | String | No | The customer's city
zip | String | No | The customer's zip code
state | String | No | The customer's state if in US/Canada
country | String | No | The customer's country

### Response Body

> The json response looks like this:

```json
{
    "id": 1,
    "inquired_for_adults": 2,
    "inquired_for_kids": 0,
    "arrival_date": "2020-05-04",
    "departure_date": "2020-05-06",
    "customer":
    {
        "id": "2",
        "name": "Customer Name",
        "email": "customeremail@example.com",
        "phone": "(123)456-7890",
        "address_line1": "Address line 1",
        "address_line2": "Address line 2",
        "city": "City",
        "zip": "12345",
        "state": "Wyoming",
        "country": "United States"
    }
}
```

The response contains the data you have submitted, + the reservation and customer id.

Key | Type | Description
--------- | ------- | -----------
id | Integer | The reservation number
inquired_for_adults | Integer | Number of adults in party
inquired_for_kids | Integer | Number of kids in party - usual quoting process then requests the birth dates; we may have to move that in this endpoint
arrival_date | String | 'YYYY-MM-DD' formatted arrival date, must be in season. 
departure_date | String | 'YYYY-MM-DD' formatted departure date.
**customer** |
id | Integer | The customer id
name | String | The customer's name (required)
email | String | The customer's email address (required
phone | String | The customer's phone number
address_line1 | String | The customer's address line #1
address_line2 | String | The customer's address line #1
city | String | The customer's city
zip | String | The customer's zip code
state | String | The customer's state if in US/Canada
country | String | The customer's country



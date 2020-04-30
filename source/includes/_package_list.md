# Building your own widget

The following endpoints are required to build your own calendar widget. If you are embedding our widget, [skip ahead](#embedding-our-widget)


## Package List

### HTTP Request

`GET /partners/packages/`

### Query Parameters

None

### Response Body

> The json response looks like this:

```json
[
{
    "id": 1,
    "name": "Package Name",
    "description": "Package Description",
    "nights": 6,
    "weekdays_arrival": [3, 6],
    "seasons": [1, 2]
},
// more packages
]
```

Key | Type | Description
--------- | ------- | -----------
id | Integer | The package's id
name | String | The package's name
description | String | The package's description
nights | Integer | Number of nights the guest will spend at the property
weekdays_arrival | [Integer] | list of weekdays allowed for check-in, 0 is Monday.
seasons | [Integer] | list of season ids during which the package is offered at some point; it may only be offered part of that season, though.



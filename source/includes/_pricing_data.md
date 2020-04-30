## Pricing Data

### HTTP Request

`GET /partners/pricing/`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------  | ------- | -----------
season_id | Yes | - | The id of the season for which you are requesting availability data 
nights | Yes | - | The length of stay you are requesting pricing data for; must correspond to the length of a package that is available during the season

### Response Body

> The json response looks like this:

```json
[
{
  "start_date": "2020-06-07",
  "end_date": "2020-06-20",
  "weekdays_arrival": [2, 6], // i.e, Wednesday and Sunday
  "low_price":
  {
      "2": ["1400.00", "1300.00", "1200.00", "1100.00", "1000.00"],
      "6": ["1200.00", "1200.00", "1200.00", "1100.00", "1000.00"]
  },
},
// more pricing periods
]
```

Key | Type | Description
--------- | ------- | -----------
start_date | String | The date the pricing period starts, in YYYY-MM-DD format
end_date | String | The date the pricing period ends, in YYYY-MM-DD format
weekdays_arrival | [Integer] | The list of (integer formatted, 0 is Monday) weekdays that are available to check-in for the length of stay you requested
low_price | {String: [String]} | A dictionary that maps the weekday of arrival to the pricing data.

The purpose of this endpoint is to enable you to give a **cheapest rate available estimate** during the early stages of the reservation process; final price will often be different, based on which accomodations are selected.

Rates should be read as the price per person for the entire length of the stay, **not** the nightly rate for the whole room like traditional accommodation.

For each available weekday, you get a list of the cheapest rates available to accommodate various size parties in a single room:

```json
"2": ["1400.00", "1300.00", "1200.00", "1100.00", "1000.00"],
```

The json on the right means that for Wednesday check-ins,

\# in party | Cheapest rate to show
-----------| ---------------------
1 | from $1400/person
2 | from $1300/person
3 | from $1200/person
4 | from $1100/person
5 | from $1000/person
6+ | from $1000/person (i.e. the minimum rate in the list)


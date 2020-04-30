## Seasons List

### HTTP Request

`GET /partners/seasons/`

### Query Parameters

None

### Response Body

> The json response looks like this:

 ```json
[
{
    "id": 1,
    "name": "Season Name",
    "dates":
    {
        "start_date": "2020-06-07",
        "end_date": "2020-09-20"
    }
},
// more seasons
]
 ```

Key | Type | Description
--------- | ------- | -----------
id | Integer | The season's id
name | String | The season's name
**dates** |
start_date | String | The date the season starts in YYYY-MM-DD format
end_date | String | The date the season ends in YYYY-MM-DD format





 ## Availability Data

 ### HTTP Request

 `GET /partners/availability/list/`

 ### Query Parameters

 Parameter | Required | Default | Description
 --------- | -------  | ------- | -----------
 season_id | Yes | - | The id of the season for which you are requesting availability data 
 
 ### Response Body

 > The json response looks like this:

 ```json
[
{
	  "id": 1,
    "name": "Room name",
    "max_occupancy": 3,
    "room_numbers": [1, 2, 3],
    "availability": [
    {
        "date": "2020-06-07",
        "available": 1,
        "available_numbers": [2]
    },
    // More availability deltas
},
// More rooms
]
 ```

 Key | Type | Description
 --------- | ------- | -----------
 id | Integer | The room type's id
 name | String | The room type's name
 max_occupancy | Integer | The maximum number of guests that can occupy the room
 room_numbers | [Integer] | Each room of this type has its own room number
 **availability** |
 date | String | The date for the availability change, in YYYY-MM-DD format
 available | Integer | The number of rooms of this time that are available on that date
 available_numbers | [Integer] | The room numbers of the rooms that are available




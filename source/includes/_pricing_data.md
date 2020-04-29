## Pricing Data

### HTTP Request

`GET /partners/property-info/`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------  | ------- | -----------

### Response Body

> The json response looks like this:

```json
{
"name": "Pitchfork Ranch", 
"slug_name": "pitchfork-ranch",
"email": "public_email@example.com",
"user_email": "private_email@example.com",
"address": "Property address",
"website": "https://pitchforkranch.example.com",
"phone": "public phone number",
"description": "Property description",
"policies_page": "https://pitchforkranch.example.com/policies",
"deposit_percentage": 30,
"balance_due": 45
}
```

Key | Type | Description
--------- | ------- | -----------
name|String|The name of the property 
slug_name|String|Slugified name of the property - useful especially when embedding the booking widget 
email|String|General email address of the property - where they wish guests to email them 
user_email|String|Email address of the Check-in Sherpa user who gave access 
address|String|Property address 
website|String|Property website URL 
phone|String|Property phone number - for guests 
description|String|Property description 
policies_page|String|URL of the page on their website that has booking policies 
deposit_percentage|Integer|% of reservation total required for initial deposit 
balance_due|Integer|# days prior to arrival when balance becomes dues. 0 means balance is due at check-out 





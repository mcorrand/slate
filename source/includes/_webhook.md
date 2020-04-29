# Tracking reservations
 
## Get notified of changes

Whenever the status of a reservation you own changes, or a payment is processed, we will post data to the URI you provided.

The payload will contain:



*   An object named ‘signature’ you will be able to use to verify the request is coming from us
*   The Id of the reservation that changed, so you can send a query to the Reservation Status endpoint and get the latest info.

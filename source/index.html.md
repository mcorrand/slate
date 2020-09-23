---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
 - python
 - ruby
 - javascript: node

toc_footers:
  - <a href='https://www.ranchbookings.com/partners/register'>Register as a partner</a>

includes:
  - resort_info
  - package_list
  - agediscounts_list
  - seasons_list
  - availability_data
  - pricing_data
  - creating_inquiry
  - embedding_widget
  - webhook
  - reservation_status

search: true
---
# Introduction

The purpose of this document is to document how to build an application on the Check-in Sherpa Platform.

All URIs are given as relative paths to the domain you are interfacing with:



*   Staging: staging.ranchbookings.com
*   Production: www.ranchbookings.com

We list what each endpoint is used for and which field, if any, is an input to any other endpoint or widget.


# Registering as a Partner

Before you are able to register an application, you need a partner account.

The Registration page is at [/partners/register](https://staging.ranchbookings.com/partners/register/)

Fill in the required information, and click the validation link in the email you receive.

Then you may login at /accounts/login

For the staging environment, we have a user already created and activated:



*   Login at [https://staging.ranchbookings.com/accounts/login](https://staging.ranchbookings.com/accounts/login)
*   Username: test_partner
*   Password: password


# Creating an application

Register an application at [/o/applications/register/](https://staging.ranchbookings.com/o/applications/register/)



*   **Logo**: an image to be displayed to end-users authorizing your application on their account. Size is 100px by 100px
*   **Name and Description**: displayed to end-users so they can identify your app
*   **Websites**: a list of websites where you will display the calendar, as full URLs, space separated. They must be secured websites (start with https). **You will not be able to embed the booking widget on any website not listed here.**
*   **Api Access**: if you are not a developer and will only use booking links/widgets, you do not need API Access. Leave this unchecked and we'll take care of authorization for you. If you do enable API Access, you get access to two more settings:
*   **Redirect URIs**: space separated list of allowed URIs you control for post-auth redirect.
*   **Universal Webhook URL**: endpoint where Check-in Sherpa will send change notifications for reservations you "own". You can subscribe to webhooks for individual resorts on your own; but this makes it much more convenient as the subscription gets created automatically upon a resort joining your app.

Once you save your application, you are redirected to a page where you can see your client_id and client_secret.


# Obtaining an Access Token

We implement the standard [OAuth2.0 authorization code flow.](https://oauth.net/2/grant-types/authorization-code/)

Here is a [detailed guide](https://developer.okta.com/blog/2018/04/10/oauth-authorization-code-grant-type).

The URIs for the flow are:



*   Authorization Page at /o/authorize/ - used to build the URL where you request access from one of our users.
*   Token Exchange Endpoint at /o/token/ - used to send a post request to obtain your access token

Here is an end-user account for the staging environment so you can test the whole flow:



*   Login at [https://staging.ranchbookings.com/accounts/login](https://staging.ranchbookings.com/accounts/login)
*   Username: admin
*   Password: password


# Using your Access Token for API queries

When sending requests, add a header:



*   Key: “Authorization”
*   Value: “Bearer {{ your access token }}”

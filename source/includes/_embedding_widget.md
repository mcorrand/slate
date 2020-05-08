# Embedding Our Widget

Instead of implementing your own booking calendar, you can embed our booking widget.
Once you have [registered an application](#creating-an-application) and [obtained authorization from a resort](#obtaining-an-access-token), you can embed their booking calendar using your app's Client Id and the resort's Slug Name that you can obtain via [the resort information endpoint](#retrieving-resort-information).

## Loading the widget

Execute the javascript on the right side in a \<script> tag near the top of the \<head> tag.
**Make sure to replace <\<DOMAIN>> with [the right domain](#introduction).**

```javascript
(function (s,h,e,r,p,a,l) {
    s['SherpaWidget']=r;s[r] = s[r] || function () { (s[r].q = s[r].q || []).push(arguments) };
    a = h.createElement(e), l = h.getElementsByTagName(e)[0];
    a.id = r; a.src = p; a.async = 1; l.parentNode.insertBefore(a, l);
}(window, document, 'script', 'sherpa', 'https://<<DOMAIN>>/widget.js'));
```

## Widget API

The widget supports two functions:

* **init** configures the widget
* **render** renders the widget; any argument passed will override any configurations from **init** or any defaults
 
**init** is mostly useful to avoid code repetition if you call **render** several times per page load, i.e. in the context of a Single Page Application.

> Here are a couple example calls:

```javascript
sherpa('init', {
  clientId: "abcdef",
  containerId: "myContainer"
})

sherpa('render', {
  resortSlug: "ExampleResort",
  modalButtons: document.getElementsByClassName("myButtonClass")
})
```
Below are the arguments supported by those functions

Parameter | Type | Required | Description
--------- | -------  | ------- | -----------
clientId | String | Yes | Your app's client id, so we can identify you have access to the resort's calendar
resortSlug | String | Yes | The resort's "slug name" obtained via [the resort information endpoint](#retrieving-resort-information).
containerId | String | No | The id for the \<div> element where you would like the calendar to be rendered. Defaults to "sherpacontainer". If not found, will create the \<div>.
modalButtons | HTMLCollection | No | If undefined, will attempt to retrieve all elements with the "sherpa-modal-button" class. If some buttons are passed-in or found via the default class, the calendar widget will load in a modal when clicking those buttons. If no buttons are found, the calendar will be rendered right in the container.



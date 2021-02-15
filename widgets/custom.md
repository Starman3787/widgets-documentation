# Custom

## Creating Custom Widgets

{% hint style="info" %}
In order to create custom widgets, you'll have to sign up for your own account.
{% endhint %}

#### Site

Creating custom widgets is a very simple:

* Navigate to [https://widgets.gg/me/custom](https://widgets.gg/me/custom)
* Click 'New'
* You have created a custom widget!



#### API

{% api-method method="post" host="https://widgets.gg/api" path="/custom" %}
{% api-method-summary %}
Create Widget
{% endapi-method-summary %}

{% api-method-description %}
Creates a new custom widget
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
API token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="image" type="string" required=false %}
Sets the image URL
{% endapi-method-parameter %}

{% api-method-parameter name="data" type="string" required=false %}
Sets the widget data
{% endapi-method-parameter %}

{% api-method-parameter name="label" type="string" required=false %}
Sets the widget label
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Custom widget creation was successful
{% endapi-method-response-example-description %}

```javascript
{
    "id": "1613396591775",
    "name": "Starman's Widget 3",
    "label": null,
    "data": null,
    "image": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No or invalid authorization provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 401,
    "message": "Unauthorized"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server-side error
{% endapi-method-response-example-description %}

```javascript
{
    "status": 500,
    "message": "Internal Server Error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Modifying the Widget

#### Site

### Name

The widget name can be changed by selecting the text, and changing it to your own. You must then click the small icon to the right to confirm your changes. This will go green if it is successful.



#### API

{% api-method method="patch" host="https://widgets.gg/api" path="/custom/:id" %}
{% api-method-summary %}
Modify Widget
{% endapi-method-summary %}

{% api-method-description %}
Modifies an existing custom widget
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
The ID of the widget to modify
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
API token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Name to modify the widget with
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Modifications were successful
{% endapi-method-response-example-description %}

```javascript
{
    "id": "1613396591775",
    "name": "pog widget",
    "label": null,
    "data": null,
    "image": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Parameters weren't provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 400,
    "message": "No name provided"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No or invalid authorization provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 401,
    "message": "Unauthorized"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Missing permissions to modify this widget
{% endapi-method-response-example-description %}

```javascript
{
    "status": 403,
    "message": "Forbidden"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server-side error
{% endapi-method-response-example-description %}

```javascript
{
    "status": 500,
    "message": "Internal Server Error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Updating the Widget

#### Site

### Label

The widget label is the text that indicates what the widget is for. It is usually on the left of the widget. It can be modified by changing the text in the 'label' box, and clicking 'save'. This will override any existing input which was there previously.

### Data

The widget data is the text which provides a value on the widget. This is usually positioned on the right. Similarly to modifying the label, this can be modified by changing the text in the 'data' box and clicking the 'save' button.

### Image

This image is added to the widget. It is usually located on the far left of the widget. This option is optional. If no image URL is provided, then no image will be added to the widget. 



#### API

{% api-method method="post" host="https://widgets.gg/api" path="/custom/:id" %}
{% api-method-summary %}
Update Widget
{% endapi-method-summary %}

{% api-method-description %}
Updates values for an existing custom widget
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
The ID of the widget to update
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
API token
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="image" type="string" required=false %}
The new widget image URL
{% endapi-method-parameter %}

{% api-method-parameter name="data" type="string" required=false %}
The new widget data
{% endapi-method-parameter %}

{% api-method-parameter name="label" type="string" required=false %}
The new widget label
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Updates were successful
{% endapi-method-response-example-description %}

```javascript
{
    "id": "1613396591775",
    "name": "pog widget",
    "label": "The answer to life, the universe, and everything",
    "data": "42",
    "image": "https://cdn.discordapp.com/attachments/711637178035339360/810962634278436894/spacexspaceforceoct2020.png"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
No id provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 400,
    "message": "No id provided"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No or invalid authorization was provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 401,
    "message": "Unauthorized"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Missing permissions to modify this widget
{% endapi-method-response-example-description %}

```javascript
{
    "status": 403,
    "message": "Forbidden"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server-side error
{% endapi-method-response-example-description %}

```javascript
{
    "status": 500,
    "message": "Internal Server Error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### 

#### Example - Discord bot using discord.js

```javascript
const fetch = ('node-fetch');
const { Client } = require('discord.js');

const client = new Client();

client.on('ready', () => {
    
    setInterval(() => {
        fetch("https://widgets.gg/api/custom/1613396591775", { // replace the ID with your custom widget ID
            method: "POST",
            headers: { Authorization: process.env.WIDGETS_GG_AUTH_TOKEN }, // provide the authentication, from an environment variable in this case
            body: JSON.stringify({
                data: client.guilds.cache.size // get the bot's server count
            })
        })
        .then(res => {
            if (res.ok) console.log("Server count updated!");
            else console.log("There was an issue with updating the server count...");
        })
        .catch(err => {
            throw err;
        });
    }, 1000 * 60 * 30); // update every 30 minutes
    
    // ...
    
});

// ...
```

## Deleting the Widget

#### Site

The widget can be deleted by clicking the 'delete' button at the bottom of the page.



#### API

{% api-method method="delete" host="https://widgets.gg/api" path="/custom/:id" %}
{% api-method-summary %}
Delete Widget
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="string" required=true %}
The ID of the widget to delete
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
API token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=202 %}
{% api-method-response-example-description %}
Widget deleted successfully
{% endapi-method-response-example-description %}

```javascript

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
No id provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 400,
    "message": "No id provided"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
No or invalid authorization was provided
{% endapi-method-response-example-description %}

```javascript
{
    "status": 401,
    "message": "Unauthorized"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Missing permissions to delete this widget
{% endapi-method-response-example-description %}

```javascript
{
    "status": 403,
    "message": "Forbidden"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Server-side error
{% endapi-method-response-example-description %}

```javascript
{
    "status": 500,
    "message": "Internal Server Error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

